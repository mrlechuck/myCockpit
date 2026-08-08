<p align="center"><img src="https://raw.githubusercontent.com/mrlechuck/CockpitBackup/main/plugin/icon.svg" width="90" alt="myCockpit"></p>

# myCockpit

Umbrella repository for my [Cockpit](https://cockpit-project.org/) plugins and
tools. Each project keeps its own repository, releases and CI, and is included
here as a **git submodule** pinned to a released version.

## Server setup

These projects run **inside Cockpit** on the Linux server. Install Cockpit first
(Debian/Ubuntu/Raspberry Pi OS shown; on Fedora/RHEL use `dnf`):

```bash
sudo apt update
sudo apt install cockpit
```

Cockpit is then reachable at `https://<server-ip>:9090`.

### Recommended components

```bash
sudo apt install cockpit-bridge cockpit-files awscli
```

- **cockpit-bridge** — the backend channel Cockpit plugins talk through (usually
  pulled in by `cockpit`, listed here to be sure).
- **cockpit-files** — file browser page, handy alongside the backup plugin.
- **awscli** — required by [CockpitBackup](https://github.com/mrlechuck/CockpitBackup)
  for S3 remote storage.

### Optional: Docker manager plugin

A third-party plugin to manage Docker/containers from Cockpit
([chrisjbawden/cockpit-dockermanager](https://github.com/chrisjbawden/cockpit-dockermanager)):

```bash
# 1. add the repo (without this, apt can't find it)
echo "deb [trusted=yes arch=all] https://chrisjbawden.github.io/cockpit-dockermanager stable main" \
  | sudo tee /etc/apt/sources.list.d/cockpit-dockermanager.list

# 2. refresh the package index
sudo apt update

# 3. install
sudo apt install dockermanager
```

## Getting started

Clone with submodules in one shot:

```bash
git clone --recurse-submodules git@github.com:mrlechuck/myCockpit.git
```

Already cloned without them? Pull the submodules in:

```bash
git submodule update --init --recursive
```

## Projects

### [CockpitBackup](https://github.com/mrlechuck/CockpitBackup)

Cockpit plugin for per-folder daily backups with restore. Local disk or Amazon S3
(and S3-compatible) storage, full or incremental archives, multiple daily runs,
tiered grandfather-father-son retention, per-folder logs and live progress.

- Repository: https://github.com/mrlechuck/CockpitBackup
- Latest release: https://github.com/mrlechuck/CockpitBackup/releases/latest
- Included at: `CockpitBackup/` (submodule)

### [CockpitBranding](https://github.com/mrlechuck/CockpitBranding)

Custom look and feel for Cockpit — colors, logo and login page, installed into
`/usr/share/cockpit/branding/`.

- Repository: https://github.com/mrlechuck/CockpitBranding
- Included at: `CockpitBranding/` (submodule)
