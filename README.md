# DRM-CLI — Deployment Release Management CLI

[![GitHub](https://img.shields.io/badge/GitHub-dband--drm%2Fdrm--cli-blue?logo=github)](https://github.com/dband-drm/drm-cli)

**DRM-CLI** is an open-source command-line tool developed by [d-band](https://github.com/dband-drm) for managing and automating database deployments across multiple environments.

> 🔗 **GitHub Repository:** [https://github.com/dband-drm/drm-cli](https://github.com/dband-drm/drm-cli)

---

## Introduction

DRM-CLI simplifies the lifecycle of database change management — from building a deployment package to executing and tracking releases across target environments.

Key features:
- Supports **SQLite**, **MSSQL**, **PostgreSQL**, and **Oracle** databases
- **Encrypted** deployment packages for secure credential handling
- **DryRun**, **Deploy**, and **Align** execution modes
- Integration with **Liquibase**, **Flyway**, and **SqlPackage**
- Structured logging with rotation and configurable verbosity
- JSON and SQLite data-store options for release tracking

---

## Getting Started

### Prerequisites

- Python 3.8+
- pip

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/dband-drm/drm-cli.git
   cd drm-cli
   ```

2. Install DRM into a target directory:
   ```bash
   python install.py
   ```
   Follow the interactive prompts to choose the installation path, data-store type (JSON or SQLite), and an optional encryption key.

   **Silent install** (non-interactive):
   ```bash
   python install.py -f /path/to/install -d sqlite -p MySecretKey
   ```

### Upgrade

If a DRM installation already exists at the target path, the installer automatically switches to upgrade mode. You can also force a silent upgrade:
```bash
python install.py -f /path/to/install
```

---

## Usage

After installation, navigate to your DRM directory and run deployments using the `drm_deploy.py` script:

```bash
cd /path/to/drm
python drm_deploy.py --mode Deploy
python drm_deploy.py --mode DryRun
python drm_deploy.py --mode Align
```

Enable verbose/trace logging with the `--trace` flag:
```bash
python drm_deploy.py --mode Deploy --trace
```

---

## Architecture

![DRM-CLI Folder Architecture](Images/drm-cli%20folder%20architecture.png)

### Deployment Flow

![Deployment Flow](Images/DeploymentFlow.png)

### Release Entity Relationship

![Release ERD](Images/ReleaseEntitiesRelationship.png)

---

## Contribute

Contributions are welcome! Please open an issue or submit a pull request on the [GitHub repository](https://github.com/dband-drm/drm-cli).

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## License

Copyright (C) 2023 d-band — All Rights Reserved.  
See [LICENSE](LICENSE) for details.