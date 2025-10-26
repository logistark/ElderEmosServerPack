# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

ElderEmosServerPack is a Minecraft modpack for version 1.21.1 using NeoForge, managed with packwiz.

**Key Details:**
- Minecraft Version: 1.21.1
- Mod Loader: NeoForge
- Pack Manager: Packwiz
- Distribution: GitHub + Prism Launcher

## Packwiz Commands

Packwiz must be installed to work with this modpack. Install with: `go install github.com/packwiz/packwiz@latest`

### Essential Commands

**Initialize packwiz (first time only):**
```bash
packwiz init
```

**Add mods:**
```bash
packwiz modrinth add <mod-slug>      # From Modrinth (preferred)
packwiz curseforge add <mod-id>       # From CurseForge
```

**Update mods:**
```bash
packwiz update <mod-name>             # Update specific mod
packwiz update --all                  # Update all mods
```

**Remove mods:**
```bash
packwiz remove <mod-name>
```

**Refresh pack metadata:**
```bash
packwiz refresh                       # Updates pack.toml and index
```

**Test locally:**
```bash
packwiz serve                         # Serves pack on localhost:8080
```

## Project Structure

```
ElderEmosServerPack/
├── pack.toml              # Main pack configuration (created by packwiz init)
├── index.toml             # Index of all mods (created by packwiz)
├── mods/                  # Individual mod .pw.toml files (auto-generated)
├── config/                # Server/client configurations (if any)
├── README.md              # User-facing documentation
├── .gitignore             # Excludes JAR files and runtime directories
└── CLAUDE.md              # This file
```

## Workflow for Adding Mods

**Each mod should be added in its own branch and pull request.**

1. **Ensure you're on an updated master branch:**
   ```bash
   git checkout master
   git pull
   ```

2. **Create a new branch for the mod:**
   ```bash
   git checkout -b add-<mod-name>
   ```

3. **Search for the mod on Modrinth:** https://modrinth.com/
4. **Copy the mod slug** (from URL: modrinth.com/mod/**slug-here**)
5. **Add the mod with packwiz:**
   ```bash
   packwiz modrinth add <slug>
   ```
   (Packwiz will automatically add dependencies)

6. **Test the pack locally** (optional but recommended):
   ```bash
   packwiz serve
   ```

7. **Commit all changes:**
   ```bash
   git add .
   git commit -m "Add <mod-name>"
   ```

8. **Push branch and create PR:**
   ```bash
   git push origin add-<mod-name>
   gh pr create
   ```

9. **After PR is merged, return to master:**
   ```bash
   git checkout master
   git pull
   ```

10. **Repeat for next mod**

## Important Notes

- **Never commit .jar files** - they're excluded in .gitignore
- **Always update index.toml** after adding/removing mods with `packwiz refresh`
- **Test compatibility** - ensure mods work with NeoForge 1.21.1
- **Check dependencies** - packwiz will auto-add required dependencies
- When creating PRs, update README.md if the mod requires special configuration
- Pack URL for distribution: `https://raw.githubusercontent.com/USERNAME/ElderEmosServerPack/main/pack.toml`

## Common Issues

- If packwiz commands fail, ensure you're in the project root directory
- If mods don't appear, run `packwiz refresh` to update index.toml
- For mod conflicts, check the crash logs in Prism Launcher
