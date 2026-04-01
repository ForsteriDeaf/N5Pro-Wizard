# N5Pro

**Self-healing Proxmox automation platform**

N5Pro is a practical automation toolkit for Proxmox VE and Proxmox Backup Server, designed for homelab and small infrastructure environments that need repeatable deployment, diagnostics, recovery, and operational workflows.

## Features

* Interactive dashboard: `n5pro`
* Diagnostics and repair: `n5pro-doctor`
* Guided healing workflow: `n5pro-heal`
* Safe updates with backup: `n5pro-update`
* Environment backups: `n5pro-backup`
* PBS bootstrap and tool deployment: `n5pro-bootstrap-pbs`
* Logs and cron automation helpers
* Local/remote version check support

## Main components

| Command               | Purpose                             |
| --------------------- | ----------------------------------- |
| `n5pro`               | Main dashboard                      |
| `n5pro-doctor`        | Diagnostics, fix, auto-fix, dry-run |
| `n5pro-heal`          | Guided repair workflow              |
| `n5pro-update`        | Repo and local binary updates       |
| `n5pro-backup`        | Backup current environment          |
| `n5pro-version`       | Version check                       |
| `n5pro-bootstrap-pbs` | Install N5Pro tools on PBS          |
| `n5pro-log`           | View/export logs                    |
| `n5pro-cron`          | Manage automation jobs              |

## Quick start

### Bootstrap installer

```bash
bash <(curl -s https://raw.githubusercontent.com/ForsteriDeaf/N5Pro-Wizard/main/final/bootstrap.sh)
```

### Post-install flow

```bash
n5pro
n5pro-update --install
n5pro-doctor
```

## Repository layout

* `final/` — stable production scripts
* `legacy/` — older scripts and deprecated logic
* `docs/` — documentation
* `screenshots/` — dashboard and workflow captures

## Documentation

* [Installation guide](docs/INSTALL.md)
* [Architecture overview](docs/ARCHITECTURE.md)
* [Recovery / reinstall guide](docs/RECOVERY.md)

## Safety model

N5Pro is designed to prefer safe operations:

* backup before major change
* dry-run support
* guided fixes
* explicit bootstrap steps for PBS
* version-aware updates

## Versioning

```bash
n5pro-version check
```

## License

MIT

## Author

Built for real-world Proxmox homelab operations.
