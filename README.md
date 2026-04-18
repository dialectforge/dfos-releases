# DialectForge OS — Releases

**The first penetration-proof operating system.**

Download pre-built bootable images of DialectForge OS.

## Latest Release: v3.0 Mesosphere

| File | Size | Description |
|------|------|-------------|
| `dfos-3.0-mesosphere-x86_64.img.zst` | — | Compressed disk image (zstd) |

### Quick Start

**1. Download** the `.img.zst` file from [Releases](https://github.com/dialectforge/dfos-releases/releases)

**2. Decompress:**
```bash
zstd -d dfos-3.0-mesosphere-x86_64.img.zst
```

**3. Flash to USB:**
```bash
sudo dd if=dfos-3.0-mesosphere-x86_64.img of=/dev/sdX bs=4M status=progress
sync
```
Or use [Etcher](https://etcher.balena.io) with the decompressed `.img` file.

**4. Boot** from USB. GRUB menu appears with:
- **Mesosphere** — normal boot
- **Safe Graphics** — for NVIDIA/AMD hardware compatibility
- **Safe Mode** — password protected, no network
- **Install** — install to internal disk

**5. Login:**
- User: `dfuser` / Password: `dialectforge`
- Root: `root` / Password: `dfroot`

### System Requirements

- x86_64 processor
- 2GB+ RAM
- UEFI boot (BIOS boot also supported)
- 8GB+ USB drive for live boot

### Verify Download

```bash
sha256sum -c SHA256SUMS
```

## What's Inside

### Core Security (unchanged from Troposphere)
- Linux 6.12.12 LTS kernel with DialectForge subsystem
- Per-process memory encryption (df_mem)
- Three-tier trust model (Native / Adopted / Quarantine)
- USB auto-quarantine
- CRYSTALS-Kyber-768 post-quantum crypto
- Encrypted filesystem (dialectfs)
- AF_DIALECTFORGE protocol family
- Anomaly detection with emergency rotation
- GRUB password-protected safe mode

### New in v3.0 Mesosphere

**Rust Userspace Tools** — static musl binaries, no runtime dependencies:
- `dfctl` — system control and configuration
- `dfpkg` — package manager with OTA update system
- `dgctl` — DialectForge gateway control
- `df_tunnel` — encrypted tunnel management

**COSMIC Desktop Environment** (epoch-1.0.8, Wayland):
- Full Wayland compositor via COSMIC
- 5 custom COSMIC panel applets:
  - `df-status` — system trust state and security posture
  - `df-network` — AF_DIALECTFORGE network status
  - `df-quarantine` — quarantine zone monitor
  - `df-usb` — USB device trust manager
  - `df-files` — dialectfs file browser integration
- greetd display manager with COSMIC greeter
- Plymouth boot splash with DF theme

**System Services:**
- PipeWire audio
- CUPS printing
- BlueZ bluetooth
- TLP power management

## Previous Releases

| Version | Codename | Notes |
|---------|----------|-------|
| v1.0 | Troposphere | Initial release — kernel + CLI userspace |

## Source Code & Tools

- **Kernel (GPL v2):** [DFoS](https://github.com/dialectforge/DFoS) — full kernel source, audit and build it yourself
- **Userspace tools:** `dfctl`, `dfpkg`, `dgctl`, `df_tunnel`, the COSMIC applets, and pentest suite are proprietary. Commercial licenses and early access available — contact dialectforge@gmail.com
- **Website:** [dialectforge.com](https://dialectforge.com)
- **Prior Art:** [DialectForge-Native Language Models](https://github.com/dialectforge/dialectforge-prompt)

## License

DialectForge protocol is Patent Pending (Provisional Application Filed February 25, 2026). Free for personal, research, and educational use. Commercial deployment requires a protocol license.

*Inventor: John Dean Martin — Ewen, Michigan*
