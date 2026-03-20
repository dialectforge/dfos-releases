# DialectForge OS — Releases

**The first penetration-proof operating system.**

Download pre-built bootable images of DialectForge OS.

## Latest Release: v1.0 Troposphere

| File | Size | Description |
|------|------|-------------|
| `dfos-1.0-troposphere-x86_64.img.zst` | ~460MB | Compressed disk image (zstd) |

### Quick Start

**1. Download** the `.img.zst` file from [Releases](https://github.com/dialectforge/dfos-releases/releases)

**2. Decompress:**
```bash
zstd -d dfos-1.0-troposphere-x86_64.img.zst
```

**3. Flash to USB:**
```bash
sudo dd if=dfos-1.0-troposphere-x86_64.img of=/dev/sdX bs=4M status=progress
sync
```
Or use [Etcher](https://etcher.balena.io) with the decompressed `.img` file.

**4. Boot** from USB. GRUB menu appears with:
- **Troposphere** — normal boot
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

## What\'s Inside

- Linux 6.12.12 LTS kernel with DialectForge subsystem
- Per-process memory encryption (df_mem)
- Three-tier trust model (Native / Adopted / Quarantine)
- USB auto-quarantine
- CRYSTALS-Kyber-768 post-quantum crypto
- Encrypted filesystem (dialectfs)
- AF_DIALECTFORGE protocol family
- Anomaly detection with emergency rotation
- GRUB password-protected safe mode

## Source Code & Tools

- **Kernel (GPL v2):** [DFoS](https://github.com/dialectforge/DFoS) — full kernel source, audit and build it yourself
- **Userspace tools:** The installer, dfctl, dfpkg, and pentest suite are proprietary. Commercial licenses and early access available — contact dialectforge@gmail.com
- **Website:** [dialectforge.com](https://dialectforge.com)
- **Prior Art:** [DialectForge-Native Language Models](https://github.com/dialectforge/dialectforge-prompt)

## License

DialectForge protocol is Patent Pending (Provisional Application Filed February 25, 2026). Free for personal, research, and educational use. Commercial deployment requires a protocol license.

*Inventor: John Dean Martin — Ewen, Michigan*
