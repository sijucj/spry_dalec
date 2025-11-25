# Spry SQLPage DALEC Packages

This repository contains DALEC-generated packages for `spry-sqlpage`, providing native installation options across multiple platforms.

## About

Spry SQLPage is a declarative web application framework built on Deno. This repository uses [DALEC](https://github.com/project-dalec/dalec) to build secure, cross-platform packages.

## Installation

### 📦 Package Managers (Recommended)

#### Ubuntu/Debian (.deb packages)

```bash
# Ubuntu (Jammy)
wget https://github.com/YOUR_USERNAME/spry_dalec/releases/latest/download/spry-sqlpage_jammy.deb
sudo dpkg -i spry-sqlpage_jammy.deb

# Debian (Bookworm)
wget https://github.com/YOUR_USERNAME/spry_dalec/releases/latest/download/spry-sqlpage_bookworm.deb
sudo dpkg -i spry-sqlpage_bookworm.deb
```

#### RHEL/Rocky Linux/Alma Linux (.rpm packages)

```bash
# Rocky Linux 9
wget https://github.com/YOUR_USERNAME/spry_dalec/releases/latest/download/spry-sqlpage_rockylinux9.rpm
sudo rpm -i spry-sqlpage_rockylinux9.rpm

# Alma Linux 9
wget https://github.com/YOUR_USERNAME/spry_dalec/releases/latest/download/spry-sqlpage_almalinux9.rpm
sudo rpm -i spry-sqlpage_almalinux9.rpm
```

#### macOS

```bash
# Download and extract
wget https://github.com/YOUR_USERNAME/spry_dalec/releases/latest/download/spry-sqlpage-macos.tar.gz
tar -xzf spry-sqlpage-macos.tar.gz
sudo mv spry-sqlpage-macos /usr/local/bin/spry-sqlpage
```

#### Windows

```powershell
# Download from releases page
# https://github.com/YOUR_USERNAME/spry_dalec/releases/latest
```

### 🔗 Direct Download

Visit our [GitHub Releases](https://github.com/YOUR_USERNAME/spry_dalec/releases) page to download pre-built binaries for your operating system:

- **Windows**: `spry-sqlpage-windows.zip`
- **macOS**: `spry-sqlpage-macos.tar.gz`
- **Linux DEB**: `spry-sqlpage_jammy.deb`, `spry-sqlpage_bookworm.deb`
- **Linux RPM**: `spry-sqlpage_rockylinux9.rpm`, `spry-sqlpage_almalinux9.rpm`

## Verification

After installation, verify that `spry-sqlpage` is working correctly:

```bash
spry-sqlpage --version
spry-sqlpage --help
```

## Building from Source

### Prerequisites

- Docker with BuildKit support
- Docker Buildx

### Build Commands

```bash
# Build DEB package for Ubuntu Jammy
docker buildx build \
  --target jammy \
  --output type=local,dest=./output \
  -f dalec-spry-sqlpage.yaml \
  .

# Build RPM package for Rocky Linux 9
docker buildx build \
  --target rockylinux9 \
  --output type=local,dest=./output \
  -f dalec-spry-sqlpage.yaml \
  .

# Build Windows package (cross-compilation)
docker buildx build \
  --target windowscross \
  --output type=local,dest=./output \
  -f dalec-spry-sqlpage.yaml \
  .
```

### Manual Compilation with Deno

```bash
# Download import_map.json
curl -o import_map.json https://raw.githubusercontent.com/programmablemd/spry/refs/heads/main/import_map.json

# Compile for your platform
deno compile \
  --allow-all \
  --import-map=import_map.json \
  --output=spry-sqlpage \
  spry_sqlpage.ts
```

## Supported Platforms

- ✅ Ubuntu 22.04 (Jammy)
- ✅ Debian 12 (Bookworm)
- ✅ Rocky Linux 9
- ✅ Alma Linux 9
- ✅ macOS (Intel & Apple Silicon)
- ✅ Windows (x64)

## Release Information

This repository is powered by [DALEC](https://github.com/project-dalec/dalec) for automated package generation and distribution. Each release includes:

- **Ubuntu packages** (.deb for jammy)
- **Debian packages** (.deb for bookworm)
- **RPM packages** (.rpm for Rocky Linux 9, Alma Linux 9)
- **Windows binaries** (.zip)
- **macOS binaries** (.tar.gz)

For the latest release notes, visit [GitHub Releases](https://github.com/YOUR_USERNAME/spry_dalec/releases).

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This packaging repository is licensed under MIT. The Spry project has its own license.

## Links

- [Spry Project](https://github.com/programmablemd/spry)
- [DALEC Documentation](https://project-dalec.github.io/dalec/)
- [Deno](https://deno.land/)

