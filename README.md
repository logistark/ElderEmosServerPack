# ElderEmosServerPack

A Minecraft modpack for version 1.21.1 using NeoForge.

## Information

- **Minecraft Version:** 1.21.1
- **Mod Loader:** NeoForge
- **Pack Manager:** Packwiz

## Requirements

- [Prism Launcher](https://prismlauncher.org/) (recommended) or another launcher
- Minecraft Java Edition 1.21.1
- Java 21 or higher
- At least 4GB of RAM allocated (6-8GB recommended)

## Installation with Prism Launcher

1. **Download and install [Prism Launcher](https://prismlauncher.org/)**

2. **Import the modpack:**
   - Click "Add Instance" in Prism Launcher
   - Select "Import from zip" or "Import"
   - Paste the pack URL: `https://raw.githubusercontent.com/YOUR-USERNAME/ElderEmosServerPack/main/pack.toml`
   - Click OK and wait for the pack to download

3. **Launch the game:**
   - Select the ElderEmosServerPack instance
   - Click "Launch"
   - The first launch will download all mods automatically

## For Developers

### Prerequisites

Install [packwiz](https://packwiz.infra.link/):
```bash
go install github.com/packwiz/packwiz@latest
```

### Clone and Setup

```bash
git clone https://github.com/YOUR-USERNAME/ElderEmosServerPack.git
cd ElderEmosServerPack
```

### Common Commands

**Add a mod from Modrinth:**
```bash
packwiz modrinth add <mod-slug>
```

**Add a mod from CurseForge:**
```bash
packwiz curseforge add <mod-id>
```

**Update all mods:**
```bash
packwiz update --all
```

**Refresh pack metadata:**
```bash
packwiz refresh
```

**Serve pack locally for testing:**
```bash
packwiz serve
```

## Contributing

Feel free to suggest mods or report issues.

## License

This modpack is provided as-is. Individual mods have their own licenses.
