# PPSSPP Helm Chart Repository

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Helm Version](https://img.shields.io/badge/Helm-v3-blue)](https://helm.sh)
[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/ppsspp-helm-chart)](https://artifacthub.io/packages/search?repo=ppsspp-helm-chart)

This repository contains a production-ready Helm chart for deploying [PPSSPP](https://docs.linuxserver.io/images/docker-ppsspp/) on Kubernetes.

## About PPSSPP

PPSSPP is a free and open-source PlayStation Portable emulator. This chart deploys the
[linuxserver.io](https://docs.linuxserver.io/images/docker-ppsspp/) build, which serves the full
emulator desktop in your browser over KasmVNC — no local install needed, play from any device on
your network:

- 🎮 Full PSP emulator desktop, streamed over the browser (KasmVNC)
- 🖥️ No client install — works from any modern browser
- 🗄️ BIOS/config/save persistence via a mounted `/config` volume
- 🎯 Bring your own ROMs/BIOS library via `extraVolumes`
- ⚡ Optional VA-API GPU passthrough for hardware-accelerated rendering

## Quick Start

### Add Helm Repository

```bash
helm repo add ppsspp https://henriqzimer.github.io/ppsspp-helm-chart/
helm repo update
```

### Install Chart

```bash
helm install ppsspp ppsspp/ppsspp
```

For detailed installation instructions and configuration options, see the [chart README](chart/README.md).

## Repository Structure

```
.
├── chart/              # Helm chart for PPSSPP
│   ├── Chart.yaml      # Chart metadata
│   ├── values.yaml     # Default configuration values
│   ├── README.md       # Detailed chart documentation
│   └── templates/      # Kubernetes manifest templates
├── LICENSE             # Repository license
└── README.md           # This file
```

## Documentation

- **[Chart Documentation](chart/README.md)** - Complete installation and configuration guide
- **[linuxserver.io PPSSPP Docs](https://docs.linuxserver.io/images/docker-ppsspp/)** - Upstream image documentation
- **[Values Reference](chart/values.yaml)** - All available configuration options

## Prerequisites

- Kubernetes 1.19+
- Helm 3.0+
- Persistent storage, if you enable `persistence.config` (NFS, local-path, or cloud storage)
- (Optional) Ingress controller
- (Optional) cert-manager for automatic TLS
- (Optional) A node exposing `/dev/dri` for GPU passthrough

## Features

This Helm chart provides:

- ✅ Production-ready Kubernetes Deployment/Service
- ✅ Optional persistent `/config` volume (BIOS, settings, saves)
- ✅ `extraVolumes`/`extraVolumeMounts` for a ROMs/BIOS library
- ✅ Optional Ingress with TLS support
- ✅ Resource limits and requests
- ✅ Readiness/liveness probes
- ✅ Configurable ServiceAccount
- ✅ Optional VA-API (`/dev/dri`) GPU passthrough

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

This Helm chart is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

PPSSPP itself is licensed under its own terms. See the [PPSSPP project](https://ppsspp.net/) and the
[linuxserver.io image](https://github.com/linuxserver/docker-ppsspp) for more information.

## Support

- 🐛 [Report Issues](https://github.com/HenriqZimer/ppsspp-helm-chart/issues)
- 💬 [Discussions](https://github.com/HenriqZimer/ppsspp-helm-chart/discussions)
- 📖 [Documentation](chart/README.md)

---

Made with ❤️ for the retro gaming community
