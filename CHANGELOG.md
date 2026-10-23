## 2.1.5 (2026-08-10)


### Bug Fixes

* **ssl:** avoid HTTPS drop on domain reorder (dd6ca3a)
* **ssl:** keep partial HTTPS while expanding SANs (4f29711)
* **ssl:** resolve cert lineage by SAN health (c090e78)
* **ssl:** use covering cert for panel domains (48f8f8d)

## 2.1.4 (2026-07-31)


### Bug Fixes

* **system:** clarify purge removes unused docklift images (97852de)
* **terminal:** clarify purge clears BuildKit cache (f357d9a)


### Features

* **db:** backfill commit_sha and image_tags columns (cdde56e)
* **db:** migrate deployment image_tags columns (270a59b)
* **db:** store deploy commit sha and image tags (8ff6f15)
* **deploy:** add keep-2 image and BuildKit helpers (404d760)
* **deploy:** keep-2 prune and restore previous API (d64d84c)
* **frontend:** add deployment commit_sha and image_tags (ed54e53)
* **frontend:** add Restore previous on deployments (802fb59)
* **git:** expose HEAD sha and hard reset helpers (cd91146)
* **system:** purge unused docklift images and BuildKit (b7a9df2)

## 2.1.3 (2026-07-26)


### Features

* **terminal:** implement shell WS auth deferral during sidebar upgrade confirmation and enhance connection handling (abccd0f)

## 2.1.2 (2026-07-26)


### Features

* **github:** include app name and slug in status response (bc623ac)
* **settings:** display GitHub app name and slug in integration section (c063d4d)

## 2.1.1 (2026-07-26)

# 2.1.0 (2026-07-26)


### Bug Fixes

* **shell:** keep sidebar active on nested routes *force minor* (b71c5cf)

## 2.0.14 (2026-07-26)

## 2.0.13 (2026-07-26)


### Bug Fixes

* **shell:** size collapsed new-project like logo (4df7e52)


### Features

* **domain:** paste urls to bare hostnames (c8ba282)
* **domains:** add panel domain card (cb37563)
* **domains:** add panel ssl events and dns-check (b562a39)
* **domains:** clean pasted hostnames on add (e1e9c4e)
* **domains:** simplify dns guide without accordion (8870208)
* **frontend:** use singular domain tab label (723978a)
* **settings:** match project domain panel ux (3951cbe)
* **shell:** avatar menu with copyable email (7017cdf)
* **website:** add changelog nav and disable html (a0ffcb9)
* **website:** add homepage changelog preview (555674a)
* **website:** load changelog releases for homepage (1ae2620)
* **website:** register changelog preview component (4056b4f)
* **website:** show changelog preview on home (da1c536)
* **website:** sync changelog from repo root (0397293)

## 2.0.12 (2026-07-26)


### Bug Fixes

* **deploy:** cancellable timed async image pull (ccebcf4)
* **deploy:** own deploy lock by deployment id (3f2d9d5)
* **deploy:** serialize cancel with ownership gates (8302e85)
* **deploy:** undo proxy links if cancel wins success-tail (190d60a)
* **frontend:** minor file tree polish (6ff9293)
* **git:** fail closed when branch or tag missing (bccadb6)
* **github:** match tag pins on webhook refs (48de2cc)
* **git:** verify tags on remote before reset (ca68e55)
* **nginx:** abort domain writes when deploy lock lost (3250898)


### Features

* **db:** fetch live engine tags from docker hub (713580e)
* **db:** persist selected version and mount path (69af7b3)
* **db:** version-aware mounts and legacy image pins (053a523)
* **frontend:** add account menu (0b76f2e)
* **frontend:** add project quick actions (87653ba)
* **frontend:** add project resource cell (465a9b3)
* **frontend:** adjust app shell chrome (e9a0990)
* **frontend:** align new project create flow (1b7a9fb)
* **frontend:** allow full-height log viewer (3e2aaab)
* **frontend:** compact project action bar (954033d)
* **frontend:** database tabs and deploy log select (814e74f)
* **frontend:** denser operate sidebar (482d22c)
* **frontend:** fill viewport for system logs (a98a535)
* **frontend:** fill viewport for terminal (1356eea)
* **frontend:** harden file editor save flow (141146d)
* **frontend:** improve attach database panel (8790694)
* **frontend:** include databases in palette (c9693c5)
* **frontend:** one-viewport logs page (5d23071)
* **frontend:** one-viewport ports page (2475f6e)
* **frontend:** one-viewport terminal page (0cefca2)
* **frontend:** polish service switcher (dae9af1)
* **frontend:** polish sidebar status (451519b)
* **frontend:** projects-style databases list (d2a32c7)
* **frontend:** raise toast provider (9921351)
* **frontend:** responsive projects dashboard (4b26d22)
* **frontend:** route docs externally and operate pages (ce268da)
* **frontend:** settings nav from shared ids (495acc2)
* **frontend:** share settings nav ids (76d342f)
* **frontend:** strengthen global toasts (2a3603b)
* **frontend:** support tag refs in branch selector (c9cc81a)
* **frontend:** update shell navigation (c94c800)
* **frontend:** version picker on new database (fbcd5f9)
* **frontend:** wire account menu in top bar (e9385c5)
* **github:** improve branch and tag listing (c1247f4)
* **ports:** expose private running projects (9be11d3)

## 2.0.11 (2026-07-25)


### Features

* **compose:** support command and skip PORT env (a4598eb)
* **db:** add engine field and database links (88418aa)
* **db:** catalog official database engines (48e9802)
* **db:** link cleanup and credential env guards (fd4e20e)
* **db:** link inject and network attach helpers (d9df90f)
* **db:** managed database create and link API (08bdfce)
* **db:** migrate managed databases schema (de3e5fc)
* **db:** mount databases router (4385532)
* **db:** repair db_engine and link indexes (e8f876a)
* **db:** unique app env key per database link (885dfe7)
* **deploy:** pull and run managed database images (f8c8b10)
* **docker:** attach containers to project networks (7137abe)
* **frontend:** add databases new route (dec97de)
* **frontend:** add managed database project fields (f9a17ae)
* **frontend:** add new database page (4434505)
* **frontend:** attach database to app panel (17dd4ff)
* **frontend:** database connection and link panel (cb7857a)
* **frontend:** route databases list to create flow (168707b)
* **frontend:** wire managed database panels (2307840)

## 2.0.10 (2026-07-25)


### Features

* **LogViewer:** add copy functionality for logs with user feedback and handling for large log buffers (966a2ea)

## 2.0.9 (2026-07-25)


### Features

* **auth:** enhance password prompt for terminal actions with customizable options (4aba31a)
* **auth:** implement step-up password requirement for system actions (52d57a4)
* **auth:** update WebTerminal component to include step-up password requirement for host actions and enhance upgrade dialog with password confirmation (14eac7c)

## 2.0.8 (2026-07-25)


### Bug Fixes

* **ui:** update LogViewer height for better responsiveness (f28ef18)


### Features

* **ui:** enhance ServiceSwitcher with scroll functionality and improved service selection (6636a63)

## 2.0.7 (2026-07-25)


### Features

* **ui:** enhance ProjectActionBar with improved styling and new danger action (262452f)

## 2.0.6 (2026-07-25)


### Bug Fixes

* **db:** drop legacy env unique after scope migrate (65093a0)


### Features

* **api:** accept service-scoped env CRUD (5b82a2a)
* **compose:** pass per-service env into compose (32025fa)
* **db:** migrate env to service-scope unique (b860238)
* **db:** scope env vars by service name (6fc6738)
* **deploy:** inject merged service env on deploy (fe6225b)
* **env:** merge shared and service-scoped vars (c7c6634)
* **env:** scope env manager by service (10d7c04)
* **types:** add env service_name field (1acef2b)
* **ui:** add all-services action bar (915f874)
* **ui:** add all-services workspace rail (a917b1d)
* **ui:** add bare button variant (61b49a1)
* **ui:** label dashboard project lifecycle actions (262702c)
* **ui:** split all-services vs service workspace (b2786f7)

## 2.0.5 (2026-07-25)


### Features

* **sidebar:** route upgrade through terminal confirm (107f971)
* **terminal:** quiet host strip and upgrade wait dialogs (b9c8c69)
* **ui:** allow hiding dialog close button (ef38ddb)

## 2.0.4 (2026-07-25)


### Features

* **install:** pin release via v= or env (47fdac6)

## 2.0.3 (2026-07-25)


### Bug Fixes

* **system:** stop caching stale no-update checks (d92f05d)
* **ui:** refresh version banner without github spam (d02911d)

## 2.0.2 (2026-07-25)


### Bug Fixes

* **github:** list repos across all installs (1a8c27c)
* **ui:** drop fake IP:null public endpoints (d4d2ea1)
* **ui:** fix domains empty-state port copy (ea7c85d)


### Features

* **ui:** show all github accounts on new project (17a513b)

## 2.0.1 (2026-07-25)


### Bug Fixes

* **build:** tighten secret and path preflight (99eb20d)
* **compose:** soft defaults without hard caps (6776480)
* **compose:** use real DEPLOYMENTS_PATH and BACKUP_PATH in dev (3a0ea45)
* **cors:** restore same-origin checks for CORS and terminal WS (ab8d93b)
* **Dashboard:** use authFetch for project list (8ca62fe)
* **Databases:** use authFetch for project list (9468d8e)
* **deploy:** safe cancel teardown and secret preflight (cfb6bbb)
* **dns:** clarify ownership check errors (a292552)
* **docker:** boot via ensureDb not db push (7098443)
* **domains:** validate panel port and block duplicate hosts (2980540)
* **EnvVarsManager:** use authFetch for env CRUD (45cd8ff)
* explain stale dependency lockfiles (652c5cc)
* **FileEditor:** use authFetch for file save (4092d2b)
* **github:** add credentials option to fetch request for GitHub manifest (996fdc8)
* **github:** harden multi-state webhook setup (efae7b6)
* **github:** multi-state setup and skip deleted branch pushes (9738720)
* **install:** align dev install onboarding (ff4523c)
* **install:** print public dashboard onboarding (b6283c1)
* **logs:** name the two nginx containers by their role (eac21ee)
* **LogViewer:** correct search highlight matching (19b7dba)
* **NewProject:** guard repos response and authFetch create (f05048c)
* **nginx:** surface reload failures instead of fake success (f28c7a4)
* **ports:** refuse delete when port still in use (82ab6ec)
* **Ports:** use authFetch for ports API (4d1025e)
* **ProjectCard:** honor HTTP errors on actions (8ec7727)
* **ProjectDetail:** abort stale history and stream error checks (0e3b4e6)
* **projects:** disconnect proxy before delete (532ddb3)
* **ServiceDomainCard:** serial domain mutations and authFetch (f63c40c)
* **Settings:** authFetch and stream failure handling (bf9eda7)
* **ssl:** make www domains explicit (2375c1c)
* **ssl:** show actionable certificate errors (828e88c)
* **status:** report mixed services as degraded (654a2ed)
* **system:** include certbot in core container lists (a00d58b)
* **system:** narrow prune and upgrade host exec (f2eab65)
* **SystemOverview:** use authFetch for system APIs (bb2418a)
* **system:** re-auth execute against JWT user (e7f9288)
* **TerminalView:** settle password cancel and authFetch (b0a8b44)
* **ui:** clarify github connect states (cfa0d0a)
* **ui:** databases page auth and copy (40f1011)
* **ui:** narrow purge to dangling images (8eb605e)
* **ui:** ports page opt-in host port copy (4d84ddd)
* **ui:** project detail degraded and safety (fb6e762)
* **ui:** reflect degraded on project cards (c60f672)
* **ui:** step-up and restore critical copy (b8e142f)
* **ui:** unique env var editing rules (055e553)
* **uninstall:** limit cleanup to docklift resources (adc0fd9)
* **uninstall:** remove all DockLift resources, spare other workloads (686b0d1)
* **upgrade:** verify stop before db snapshot (574f26b)


### Features

* add automatic builds and persistent storage (968e324)
* **api:** seal middleware and setup rate limits (38f515c)
* **AppShell:** focus trap mobile drawer (a8b9ac6)
* **auth:** add password step-up helper (4c82c27)
* **auth:** authFetch clears session on 401 (ef8c2c2)
* **auth:** claim bootstrap and issue pwdv on session tokens (d67d209)
* **AuthProvider:** register 401 logout handler (886cebf)
* **auth:** require pwdv claim to match passwordChangedAt (1900f3a)
* **backup:** consistent SQLite snapshot and honest restore status (03ff7d7)
* **backup:** fail-closed restore and critical clear (860c18a)
* **bootstrap:** atomic claim and recover stale registration claims (3e54e99)
* **certs:** improve SSL activity events and renew handling (dc25eed)
* **CommandPalette:** focus trap and authFetch (2adf044)
* **compose:** dedupe colliding scanned service names (2ecf7ab)
* **compose:** set BACKUP_PATH and DATA_PATH in production (f885547)
* **compose:** verify teardown by exact labels (8329ca7)
* **config:** add backupPath configuration to specify backup directory location (7b728d8)
* **db:** add checked-in init migration (418b303)
* **db:** add host-port and secret env fields (d326d52)
* **db:** ensure migrate deploy on boot (4186e3f)
* **deploymentRecovery:** reconcile stale builds on boot (45372f4)
* **deployments:** add pagination support and metadata option for listing deployments (19a1877)
* **deployments:** harden cancel, scrub, ports, and status sync (b4ac11c)
* **deploymentState:** track in-flight project deploys (2a823b8)
* **dnsCheck:** DNS preflight helpers for custom domains (f9ca685)
* **DnsGuideCard:** introduce DnsGuideCard component for DNS setup guidance, including A-record examples and Cloudflare notes (eba4d58)
* **docker:** connect proxy to project networks (8a4ec96)
* **domain:** add domain input normalization and validation functions for improved hostname handling (88ba0c7)
* **domainOwnership:** reject duplicate hostnames (1b52d39)
* **env:** dedupe env variables on boot (117309d)
* **focusTrap:** trap and restore focus for overlays (52f5851)
* **frontend:** add degraded project status type (07e1441)
* **fsCopy:** implement cross-platform recursive directory copy and atomic swap functions (846ae38)
* **index:** maintenance gate and boot deployment recovery (fe63c10)
* **logs:** add certbot stream and follow the tail reliably (c678a7a)
* **maintenance:** add process-wide maintenance gate to manage API access during restore operations (1db75ee)
* **naming:** add path hash helpers for service and storage keys (20004b9)
* **naming:** add project network name helper (bf5b5e7)
* **networking_proxy:** enhance SSL issuance process with DNS preflight checks and activity logging (ce35705)
* **nginx:** enhance SSL event logging during Nginx configuration updates for better error handling and user feedback (7dc21ca)
* **portAllocation:** allocate host ports atomically (acccfd6)
* **ProjectDetail:** implement deployment history pagination and enhance real-time log tracking (5247cfe)
* **ProjectDetail:** integrate DNS management components and streamline domain handling (434605f)
* **projects:** rollback create failures and block delete while deploying (8bb04a9)
* **projectStatusSync:** sync status from all service containers (5556a8e)
* **restore:** add commit-or-rollback policy (31cefc2)
* **restore:** add restore lock helper (8ef8c9a)
* **restore:** add setup-token restore auth (7987dde)
* **restore:** persist critical seal marker (37c4363)
* **runCompose:** safe docker spawn with error and close handlers (eb62c3d)
* **ServiceDomainCard:** add ServiceDomainCard component for managing service domains, SSL status, and DNS checks (a29f5df)
* **shell:** add expandedOnHover prop to Sidebar for improved user experience (0d288a2)
* **shell:** enhance sidebar interaction with hover state (9572ddb)
* **sslHelp:** implement SSL error handling with user guidance for common certbot issues (7a4e335)
* **streamProgress:** implement function to consume text streaming responses and handle errors (d19f89d)
* **types:** add SslEvent and DomainDnsCheck interfaces for enhanced event logging and DNS status tracking (b0e79bf)
* **ui:** rebuild dashboard around a left sidebar shell (55a0622)
* **ui:** require password for restore dialogs (e75dfa6)
* **ui:** show degraded status badge (ba25e27)

# 2.0.0 (2026-07-24)


### Bug Fixes

* **backup:** redeploy from project root after restore (ede06d2)
* **frontend:** harden SSE usage and adaptive polling (1f84a4f)
* **scripts:** align install flow with certbot and public :8080 (2e839e3)
* **security:** scrub git remotes and require webhook secret (33ca1d4)


### Features

* **auth:** split bearer and SSE auth middleware (f8e03ef)
* **deploy:** cancel builds and fix status lifecycle (262dd5c)
* **frontend:** migrate dashboard from Next.js to Vite (39801ff)
* **security:** harden auth, CORS, uploads, and GitHub CSRF (cde084b)
* **ssl:** add Let's Encrypt ACME and HTTPS vhosts (79b1b9e)
* Vite frontend and SSL *force major* (3108c66)
* Vite frontend and SSL *force major* (d08a4c8)

## 1.3.21 (2026-05-12)


### Features

* **docker:** re-enable IPv6 support and configure subnets for docklift_network in Docker Compose files (4a1431a)

## 1.3.20 (2026-05-12)


### Features

* **docker:** remove IPv6 support and subnet configurations from Docker Compose files (16748ca)

## 1.3.19 (2026-05-10)


### Features

* **deployments:** update service domains on stop and cancel actions (479a4c7)

## 1.3.18 (2026-05-10)


### Bug Fixes

* **dashboard:** prevent polling interval from resetting on buildingCount change (0cbf936)
* **deployments:** improve security by scrubbing GitHub tokens and preventing command injection (4aa5cd7)
* **github:** verify webhook signature before database lookups (747683d)
* **settings:** download backup using fetch instead of window.open (e7259fa)
* **terminal:** add input validation to prevent command injection (86714ab)
* **TerminalView:** prevent memory leak by cleaning up contextmenu listener (5f95ef7)


### Features

* add system routes for monitoring, server controls, and command execution. (65918e0)
* **docker:** enable IPv6 support and configure subnets for docklift_network (4e0c943)
* enable IPv6 support and configure subnets for docklift_network (c786ccd)
* Establish core application structure for project deployment, including a frontend dashboard and backend Docker services. (d38f3e3)
* Implement core application features including settings, GitHub integration, domain management, and system backups. (004d26c)
* **setup:** add setup token for unauthenticated backup restore (e461826)
* update dependencies in package.json and bun.lock (36d849c)
* update package dependencies and add overrides for brace-expansion (d46b83d)

## 1.3.17 (2026-02-17)


### Bug Fixes

* **nginx:** use dynamic Connection header for WebSocket proxying (1ebd6c5)


### Features

* **nginx-proxy:** route unmatched domains to docklift dashboard (3c5404d)
* **nginx:** add WebSocket upgrade support via connection header mapping (7aa4c26)

## 1.3.16 (2026-02-17)


### Bug Fixes

* **nginx:** conditionally set Connection header for WebSocket upgrade (1ddb1c7)

## 1.3.15 (2026-02-17)


### Bug Fixes

* **TerminalView:** handle missing API_URL for WebSocket connection (cb6ab60)
* update import path for Next.js routes type definitions (4f4dbcf)


### Features

* **nginx:** add WebSocket proxy configuration for terminal (8c4354d)
* **terminal:** add clipboard support with copy/paste shortcuts (105171d)
* **terminal:** add colorful prompt and set initial working directory (5781ca4)
* **terminal:** add fullscreen toggle functionality (ae6735b)
* **terminal:** add WebSocket-based interactive PTY shell service (6f1a5dd)
* **terminal:** attach WebSocket server to HTTP server (d787879)
* **terminal:** replace node-pty with script-based shell for zero native dependencies (5b6544e)
* **terminal:** replace static command logs with interactive xterm.js shell (3125827)

## 1.3.14 (2026-02-17)

## 1.3.13 (2026-02-17)


### Bug Fixes

* **auth:** allow query param tokens with purpose field for backward compatibility (0a39654)
* **deployments:** prevent write errors when response stream ends (b3b76ab)
* **domains:** enforce consistent domain validation across endpoints (d19c13f)
* **files:** add project ID validation and improve path traversal protection (90f5cd7)
* **projects:** handle upload directory creation and cleanup temp files (287d884)
* **security:** enhance CORS and restore endpoint security (1205159)
* update Next.js routes type import path (4dd89eb)


### Features

* **auth:** add setup token for fresh install and short-lived SSE token (cb62d80)
* **logs:** fetch short-lived SSE token for container logs (f731c0e)
* **system-logs:** implement SSE token auth with exponential backoff (acdcc80)
* **system:** add audit logging and password verification for execute endpoint (6bf8977)
* **terminal:** add password verification for command execution (b002974)

## 1.3.12 (2026-02-17)


### Features

* add deployments routes for project build, deploy, service management, and logging. (06698e3)
* Document the automated release process in a new skill and update README to reflect semantic-release usage. (64caccf)

## 1.3.11 (2026-02-16)


### Bug Fixes

* **backup:** specify project name in docker compose up during restore (1f5bd1c)
* correct import path and icon props for Next.js build (016fa09)
* **deployments:** pass branch parameter to pullRepo function (8caa8e7)
* **docker:** prevent write-after-end crashes in container log streaming (b9b3c52)
* **frontend:** improve SSE URL handling in SystemLogsPanel for production environments (a371253)
* **frontend:** limit container logs to 5000 lines and fix SSE URL (f3b761e)
* **frontend:** resolved LucideProps type error and added logs page (4c650ca)
* **frontend:** use relative SSE paths in production to avoid buffering (c0d08cd)
* **git:** replace git pull with fetch+reset for reliable sync (6c6224f)


### Features

* add container logs API endpoints for real-time streaming (ab1083b)
* add logs API endpoint with authentication middleware (9c8fd07)
* add logs page navigation to header (61b0149)
* add version checker component to root layout (087a8fb)
* **backup:** automate system reconciliation after restore (b96511e)
* **docker:** add real-time container log streaming via SSE (9b00f9f)
* **frontend:** add system logs panel component for real-time service monitoring (d5f4d1a)
* **frontend:** add version checker component for auto-refresh on deploy (9adf817)
* **frontend:** create logs page for real-time system logs monitoring (cd914dd)
* **health:** add version and instance ID to health endpoint (77ecf3d)
* **logs:** enhance log viewer with timestamps and improved UI (2165389)
* **logs:** increase default log tail lines to 5000 (3f32d6b)
* **logs:** introduce unified LogViewer component with search and enhanced UI (ce551ef)
* **nginx:** add configuration for long-lived SSE log streams (fbaf00a)
* **nginx:** configure Nginx for Server-Sent Events by disabling buffering and caching (edbbd62)
* **projects:** add real-time container logs viewer with ANSI support (34a9f0d)
* **system:** add real-time container logs endpoint via SSE (f8d9aa1)

## 1.3.10 (2026-01-27)


### Bug Fixes

* **projects:** update GitHub URL regex to support dots in repo names (ed99465)

## 1.3.9 (2026-01-27)


### Bug Fixes

* **deployments:** ensure consistent status updates for projects and services (bcd6020)
* **deployments:** update project and services status consistently during operations (e7ef986)
* **projects:** skip auto-sync during project builds (694b9ec)


### Features

* **deployment:** improve project status tracking and polling (97779ea)
* **deployments:** improve real-time deployment logs handling (7c322ad)
* **github:** fetch all repository pages for installations (2c22365)
* Introduce agent skills for general development, database management, and Docker operations. (01f1281)

# 1.4.0 (2026-01-27)


### Bug Fixes

* **deployments:** ensure consistent status updates for projects and services (bcd6020)
* **deployments:** update project and services status consistently during operations (e7ef986)
* **projects:** skip auto-sync during project builds (694b9ec)


### Features

* **deployment:** improve project status tracking and polling (97779ea)
* **deployments:** improve real-time deployment logs handling (7c322ad)
* **github:** fetch all repository pages for installations (2c22365)
* Introduce agent skills for general development, database management, and Docker operations. (01f1281)
