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

Install [GitHub CLI](https://cli.github.com/):
```bash
# Arch Linux
sudo pacman -S github-cli

# Then authenticate
gh auth login
```

### Clone and Setup

```bash
git clone https://github.com/logistark/ElderEmosServerPack.git
cd ElderEmosServerPack
```

### Workflow: Adding a Mod

**Each mod should be added in its own branch and pull request.**

1. **Update master branch:**
   ```bash
   git checkout master
   git pull
   ```

2. **Create a new branch:**
   ```bash
   git checkout -b add-<mod-name>
   ```

3. **Add the mod:**
   ```bash
   packwiz modrinth add <mod-slug>
   # or
   packwiz curseforge add <mod-id>
   ```

4. **Test locally (optional):**
   ```bash
   packwiz serve
   ```

5. **Commit and push:**
   ```bash
   git add .
   git commit -m "Add <mod-name>"
   git push origin add-<mod-name>
   ```

6. **Create pull request:**
   ```bash
   gh pr create
   ```

7. **After merge, return to master:**
   ```bash
   git checkout master
   git pull
   ```

### Other Useful Commands

**Update all mods:**
```bash
packwiz update --all
```

**Refresh pack metadata:**
```bash
packwiz refresh
```

**Remove a mod:**
```bash
packwiz remove <mod-name>
```

## Contributing

Feel free to suggest mods or report issues.

## License

This modpack is provided as-is. Individual mods have their own licenses.
