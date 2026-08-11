# PalForge

A desktop mod manager for **Palworld**, designed to make installing and managing mods simple, safe, and consistent.

PalForge analyzes mod archives, identifies how they should be installed, and places them in the correct location without requiring users to understand every Palworld modding framework or folder structure.

> **Status: Developer Preview**
>
> PalForge is under active development and is not yet ready for general release.

---

## What is PalForge?

Palworld mods use several different installation methods.

Depending on the mod, users may need to work with UE4SS, PalSchema, LogicMods, Pak files, Blueprint Mods, or other structures — each with different installation locations and requirements.

PalForge is designed to bring these different methods into one workflow:

**Add a mod → Identify it → Review it → Install it**

Instead of manually inspecting archives and copying files into different game directories, PalForge handles the installation structure while keeping the user in control whenever a decision is required.

---

## Current Features

### Mod Detection

PalForge analyzes ZIP archives and automatically determines their installation type based on their internal structure.

Current detection supports:

- UE4SS Framework
- UE4SS Mods
- UE4SS Lua Mods
- PalSchema Framework
- PalSchema Mods
- Blueprint Mods
- LogicMods
- Pak Mods

PalForge can also use SHA-256 hashes, aliases, and its local mod database to recognize previously identified mods.

### Identify

When PalForge cannot reliably recognize a local mod, users can identify it manually.

An identified mod can store information such as:

- Mod name
- Mod type
- Source URL
- Required dependencies

PalForge saves this information to its local database, allowing the same mod archive to be recognized again.

### Detection Override

Automatically detected mod types can be manually overridden before installation.

PalForge distinguishes between automatic detection and information confirmed through its local database.

This allows users to correct an installation type without silently changing saved mod information.

### Mod Installation

PalForge installs supported mods directly into the appropriate location inside the Palworld installation.

The current installer includes:

- Automatic installation path handling
- Palworld installation validation
- Existing file and folder detection
- Replace or skip conflict handling
- Automatic backup before replacement
- Protection against installing unresolved `Unknown` mods

### Installed Mods

PalForge can inspect the current Palworld installation and display detected installed mods.

Installed mod management is currently functional in an early form and will continue to evolve as the project develops.

### Localization

PalForge currently supports:

- English
- 繁體中文

The interface language can be selected on first launch and changed later from within PalForge.

---

## Project Principles

PalForge is built around a few core principles:

- **Keep mod installation simple.**
- **Do not silently guess when PalForge is uncertain.**
- **Give users control over installation decisions.**
- **Respect mod authors and original distribution sources.**
- **Avoid unnecessary modification of the game installation.**
- **Back up existing files before replacing them.**

PalForge is intended to manage mods from their original sources rather than independently redistributing third-party mods.

---

## Platform Support

PalForge currently targets:

**Windows • Steam version of Palworld**

Other Palworld platforms and Dedicated Server management are not currently supported.

---

## Development Status

PalForge is currently a **Developer Preview**.

The core local mod workflow is functional, including:

- Archive scanning
- Mod type detection
- Local mod identification
- Detection overrides
- Mod installation
- Existing file handling
- Automatic backups
- Installed mod inspection
- Localization

The application is still under active development. Its interface, internal APIs, database format, and workflows may change before the first public release.

PalForge should currently be considered development software.

For future development plans and milestones, see [ROADMAP.md](ROADMAP.md).

---

## Screenshots

Coming soon.

---

