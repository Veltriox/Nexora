---
layout: home
title: Nexora
hero:
  name: Nexora
  text: Futuristic · Versatile
  tagline: A flexible technology brand that could expand beyond hosting into developer tools and AI infrastructure.
  actions:
    - theme: brand
      text: Quick Start
      link: /guide/quick-start
    - theme: alt
      text: GitHub Repo
      link: https://github.com/Veltriox/Nexora
    - theme: alt
      text: Useful Commands
      link: /guide/commands
features:
  - title: One-command install
    details: curl install on Ubuntu/Debian. Dashboard at SERVER_IP:8080 with a one-time setup code.
    link: /guide/installation
    linkText: Installation
  - title: Git to deploy
    details: GitHub App, Dockerfile or Railpack builds, multi-service projects, auto-deploy on push.
    link: /guide/deployment
    linkText: Deployment
  - title: Domains & HTTPS
    details: Custom domains with Let's Encrypt. Host ports stay opt-in — domains preferred.
    link: /guide/domains
    linkText: Custom domains
  - title: Managed databases
    details: Postgres, MySQL, MariaDB, Redis, Mongo — private by default, linkable into apps.
    link: /guide/databases
    linkText: Databases
  - title: Ops toolbox
    details: System stats, web terminal, logs, backup/restore, and a full commands reference.
    link: /guide/commands
    linkText: Commands
  - title: Open source
    details: Your server, your data. Coolify / Dokku / CapRover-style workflow with a real UI.
    link: /guide/introduction
    linkText: Introduction
---

## Install in one line

```bash
sudo bash install.sh
```

Then open `http://SERVER_IP:8080`, paste the setup code from the installer output, and create your admin account.

[Continue with Quick Start →](/guide/quick-start)

<ChangelogPreview />
