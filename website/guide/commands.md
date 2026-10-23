# Commands Reference

End-to-end reference for install, day-to-day ops, logs, nginx, password reset, networking, and versioning.

| Item | Value |
|------|--------|
| Compose services | `backend` · `frontend` · `nginx` · `nginx-proxy` · `certbot` |
| Container names | `nexora-backend` · `nexora-frontend` · `nexora-nginx` · `nexora-nginx-proxy` · `nexora-certbot` |
| App containers | `nx_<project-slug>_<id>_<service>` (e.g. `nx_python-smoke_53b01966_app`) |
| Dashboard | `http://SERVER_IP:8080` |
| App publish ports | `5500`–`5600` (opt-in) |
| Fresh setup | Bootstrap secret from `docker logs nexora-backend` or `data/.bootstrap-secret` |

Run Compose commands from `/opt/nexora` on production installs (or your clone path).

## 1. Install / start / stop

```bash
# Fresh install
sudo bash install.sh
```

```bash
# Fresh install — pin a release
sudo bash install.sh v=2.0.2
```

```bash
# From a cloned repo
cd /opt/nexora
docker compose up -d --build
```

```bash
# First boot: Dashboard URL + Setup code
docker logs nexora-backend 2>&1 | grep -A8 'Fresh install'
sudo cat /opt/nexora/data/.bootstrap-secret
```

```bash
# Start / stop / restart (all)
docker compose start
docker compose stop
docker compose restart
```

```bash
# Rebuild one service (Compose service keys, not container names)
docker compose up -d --build backend
docker compose up -d --build frontend
docker compose up -d --build nginx
docker compose up -d --build nginx-proxy
```

```bash
# Status
docker compose ps
docker ps --filter name=nexora --filter name=nx_
```

## 2. Upgrade & uninstall

```bash
# Safe upgrade (keeps data + user app containers)
sudo bash upgrade.sh
```

```bash
# Full uninstall (destructive — deletes Nexora data)
sudo bash uninstall.sh -y
```

```bash
# Development build (unreleased)
sudo bash install-dev.sh
```

## 3. Logs (all services)

### Platform containers

```bash
# Compose (all services, live)
docker compose logs -f
docker compose logs -f --tail 100 backend
docker compose logs -f --tail 100 frontend
docker compose logs -f --tail 100 nginx
docker compose logs -f --tail 100 nginx-proxy

# By container name
docker logs nexora-backend -f --tail 100
docker logs nexora-frontend -f --tail 100
docker logs nexora-nginx -f --tail 100          # dashboard gateway (:8080)
docker logs nexora-nginx-proxy -f --tail 100    # custom domains (:80/:443)
docker logs nexora-certbot -f --tail 50         # Let's Encrypt renewals
```

### Deployed project apps

```bash
docker ps --filter name=nx_
docker logs nx_python-smoke_53b01966_app -f --tail 200
```

### In the UI

Dashboard → **Logs** → Backend · Frontend · Nginx Proxy · Nginx (SSE live stream).

## 4. Nginx (gateway + app proxy)

| Container | Role | Host port | Config |
|-----------|------|-----------|--------|
| `nexora-nginx` | Dashboard gateway (`/`, `/api`, `/ws`) | **8080** | repo `nginx.conf` |
| `nexora-nginx-proxy` | User app domains + HTTPS | **80**, **443** | `nginx-proxy/conf.d/*.conf` |
| `nexora-certbot` | Let's Encrypt ACME | — | `nginx-proxy/certbot/` |

```bash
# Test config then reload (gateway)
docker exec nexora-nginx nginx -t
docker exec nexora-nginx nginx -s reload

# Test config then reload (app domain proxy)
docker exec nexora-nginx-proxy nginx -t
docker exec nexora-nginx-proxy nginx -s reload

# List generated domain configs
ls -la /opt/nexora/nginx-proxy/conf.d/
```

Edit gateway routing: change `nginx.conf`, then:

```bash
docker compose up -d --force-recreate nginx
# or: docker exec nexora-nginx nginx -s reload  (if only conf mounted)
```

## 5. Reset admin password

### Production (Docker)

```bash
docker exec -it nexora-backend node dist/scripts/reset-password.js
```

Prints a new random password for the admin user. Change it after login.

### Local development

```bash
cd backend
bun run reset-password
```

## 6. Version (check & release)

### See current version

```bash
grep '"version"' backend/package.json frontend/package.json
```

```bash
curl -s http://SERVER_IP:8080/api/health
# or from the server:
curl -s http://127.0.0.1:8080/api/health
```

UI also shows the version in the header / footer (authenticated compare).

### After an update on a server

```bash
sudo bash upgrade.sh
```

## 7. Projects & containers

```bash
docker ps -a --filter name=nexora --filter name=nx_
docker inspect nx_python-smoke_53b01966_app
docker exec -it nexora-backend sh
docker exec -it nx_python-smoke_53b01966_app sh
```

Naming:

- Compose project / image prefix: `nx-<slug>-<8charId>`
- Container: `nx_<slug>_<8charId>_<service>`

## 8. Network & ports

```bash
docker network inspect nexora_network
docker network ls --filter label=com.nexora.managed=true

sudo ss -tulpn | grep -E ':(80|443|8080|550[0-9]|8000)\b'
sudo fuser -k 5500/tcp
```

| Port | Use |
|------|-----|
| `8080` | Dashboard (gateway nginx) |
| `80` | Custom domains HTTP + ACME |
| `443` | Custom domains HTTPS |
| `5500`–`5600` | Published app ports (opt-in pool) |
| `8000` | Backend (internal / local dev) |
| `3600` | Vite frontend (local `bun run dev`) |

Compose env defaults:

```bash
# PORT_RANGE_START=5500
# PORT_RANGE_END=5600
# DASHBOARD_BIND=0.0.0.0
```

## 9. Clean / reset

```bash
# Stop stack (keeps volumes/data dirs)
docker compose down

# Stop + remove containers/network (data dirs on disk remain)
docker compose down --remove-orphans

# Free stuck app port pool
for port in {5500..5600}; do sudo fuser -k ${port}/tcp 2>/dev/null; done
```

Nuclear remove: see uninstall in §2.

Volumes labelled for a project:

```bash
docker volume ls --filter label=com.nexora.project
```

## 10. Local development

```bash
cd backend
cp .env.local.example .env.local
bun install
bun run db:generate
bun run db:push
bun run dev            # http://localhost:8000
```

```bash
cd frontend
bun install
bun run dev            # http://127.0.0.1:3600
bun run build          # production → dist/
```

```bash
cd backend
bun run db:studio
bun run db:push
bun run db:generate
```

```bash
curl -s http://127.0.0.1:8000/api/health
curl -s http://127.0.0.1:3600/api/auth/status   # via Vite proxy
```

### Database scripts (from `backend/`)

| Command | Description |
|---------|-------------|
| `bun run db:studio` | Prisma Studio GUI |
| `bun run db:migrate` | Apply checked-in Prisma migrations |
| `bun run db:ensure` | Production DB bootstrap (dedupe + migrate + repair) |
| `bun run db:generate` | Regenerate Prisma client |
| `bun run db:push` | Local-only schema sync (not used on container boot) |

## Quick cheat sheet

| Task | Command |
|------|---------|
| Start stack | `docker compose up -d --build` |
| Upgrade server | `sudo bash upgrade.sh` |
| Backend logs | `docker logs nexora-backend -f` |
| Frontend logs | `docker logs nexora-frontend -f` |
| Gateway nginx logs | `docker logs nexora-nginx -f` |
| Domain proxy logs | `docker logs nexora-nginx-proxy -f` |
| Reload domain nginx | `docker exec nexora-nginx-proxy nginx -s reload` |
| Reset password | `docker exec -it nexora-backend node dist/scripts/reset-password.js` |
| Check version file | `grep version backend/package.json` |
| Health | `curl -s http://SERVER_IP:8080/api/health` |
| List apps | `docker ps --filter name=nx_` |
