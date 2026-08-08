<p align="center"><img src="https://raw.githubusercontent.com/mrlechuck/CockpitBackup/main/plugin/icon.svg" width="90" alt="myCockpit"></p>

# myCockpit

Umbrella repository for my [Cockpit](https://cockpit-project.org/) plugins and
tools. Each project keeps its own repository, releases and CI, and is included
here as a **git submodule** pinned to a released version.

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
