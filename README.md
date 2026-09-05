# PalForge

A diagnostics and testing toolkit for **Palworld** modding.

PalForge is designed to help mod users, mod authors, and troubleshooters understand what is actually installed in a modded Palworld environment, identify suspicious configurations, isolate failures, and collect useful diagnostic information when something goes wrong.

> **Status: Developer Preview**
>
> PalForge is under active development.
> The project is currently being redefined around mod diagnostics, testing, and troubleshooting.

---

## What is PalForge?

Installing a Palworld mod is only part of the problem.

A modded Palworld installation may contain mods from Steam Workshop, CurseForge, Nexus Mods, manual installations, or other sources. It may also contain frameworks and dependencies such as UE4SS and PalSchema, as well as files left behind by older installations.

When something stops working, determining the actual state of the game installation can be difficult.

PalForge aims to make that process easier.

Instead of replacing existing mod distribution platforms, PalForge is being developed as a source-independent diagnostics and testing layer for Palworld modding.

The long-term workflow is:

**Inspect → Diagnose → Isolate → Report**

PalForge should help answer questions such as:

- What mods and modding frameworks are actually installed?
- Where did they come from, when that can be determined?
- Are multiple or legacy framework installations present?
- Are files installed in unexpected locations?
- What changed between a working and broken environment?
- Which mods should be tested when isolating a failure?
- What information should be included when reporting a problem to a mod author?

PalForge does not need to replace Steam Workshop, CurseForge, Nexus Mods, or other mod distribution platforms.

Its goal is to understand the final Palworld environment regardless of how the mods arrived there.

---

## Current Development Direction

PalForge is currently being redefined around four primary areas.

### Environment Inspection

PalForge will inspect the complete Palworld modding environment rather than only the mods it installed itself.

Planned diagnostics include:

- Installed mod discovery
- UE4SS installation and version detection
- PalSchema detection
- Mixed installation source detection
- Legacy or duplicate framework detection
- Unexpected mod files and locations
- Dependency inspection
- Game and platform information
- Relevant log and crash information

The goal is not to assume that every unusual configuration is broken.

PalForge should report what it finds, explain why something may be suspicious, and allow the user or mod author to make the final decision.

### Environment Health

PalForge will use conservative diagnostic rules to highlight configurations that may cause problems.

For example:

- Multiple UE4SS installations
- Legacy UE4SS loader files
- Duplicate mods
- Missing dependencies
- Mods installed in unexpected locations
- Mixed manual and managed installations
- Other environment inconsistencies

Diagnostic findings should distinguish between confirmed problems and potential problems.

PalForge should never claim that two mods are incompatible without sufficient evidence.

### Guided Failure Isolation

When the environment appears valid but a problem remains, PalForge aims to assist with controlled troubleshooting.

Instead of manually enabling and disabling dozens of mods without keeping track of the results, users will be able to run diagnostic sessions that record:

- Which mods were enabled
- Which mods were disabled
- Whether the problem was reproduced
- Previous test results
- Remaining suspects

For suitable problems, PalForge may use divide-and-test strategies to reduce the number of tests required.

This process is intended to assist troubleshooting, not to guarantee that a single mod is responsible for every failure.

### Diagnostic Reports

PalForge aims to generate structured diagnostic reports that can be shared with mod authors or support communities.

A report may contain information such as:

- Palworld version and platform
- Installed frameworks and versions
- Active mod manifest
- Installation sources when identifiable
- Environment warnings
- Relevant configuration information
- UE4SS logs
- Crash information
- Diagnostic session results

The goal is to reduce the amount of back-and-forth required to reproduce and troubleshoot mod-related problems.

Diagnostic exports should clearly show what information will be included and avoid collecting unnecessary personal information.

---

## Existing Foundation

PalForge originally began as a local Palworld mod manager.

That work now provides the foundation for its diagnostics and testing capabilities.

The current Developer Preview already includes:

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

PalForge can install supported local mods into the appropriate Palworld location.

The existing installer includes:

- Automatic installation path handling
- Palworld installation validation
- Existing file and folder detection
- Replace or skip conflict handling
- Automatic backup before replacement
- Protection against installing unresolved `Unknown` mods

Installation remains available as a utility, but it is no longer intended to be the primary purpose of PalForge.

### Installed Mods

PalForge can inspect the current Palworld installation and display detected installed mods.

This capability will be expanded as part of the new environment inspection and diagnostics system.

### Localization

PalForge currently supports:

- English
- 繁體中文

The interface language can be selected on first launch and changed later from within PalForge.

---

## What PalForge Is Not

PalForge is not intended to replace:

- Steam Workshop
- CurseForge
- Nexus Mods
- Vortex
- Other mod distribution platforms

These platforms are better suited for discovering, downloading, publishing, and updating mods.

PalForge instead focuses on what happens after mods from different sources reach the same Palworld installation.

It is also not intended to automatically declare every detected overlap or unusual file a conflict.

Diagnostics should provide evidence, context, and reproducible information rather than guesses presented as facts.

---

## Project Principles

PalForge is built around a few core principles:

- **Inspect the environment that actually exists.**
- **Do not silently guess when PalForge is uncertain.**
- **Distinguish evidence from suspicion.**
- **Make troubleshooting reproducible.**
- **Give users and mod authors useful diagnostic information.**
- **Remain independent of any single mod distribution source.**
- **Respect mod authors and original distribution sources.**
- **Avoid unnecessary modification of the game installation.**
- **Back up files before performing destructive operations.**
- **Collect only the diagnostic information that is necessary.**

PalForge is intended to work alongside existing mod platforms rather than independently redistributing third-party mods.

---

## Platform Support

PalForge currently targets:

**Windows • Steam version of Palworld**

Other Palworld platforms and Dedicated Server management are not currently supported.

---

## Development Status

PalForge is currently a **Developer Preview**.

The existing local mod-management foundation is functional, including:

- Archive scanning
- Mod type detection
- Local mod identification
- Detection overrides
- Mod installation
- Existing file handling
- Automatic backups
- Installed mod inspection
- Localization

The project is now entering a new stage of development focused on validating PalForge as a diagnostics and testing toolkit.

The first priority of this new direction is environment inspection: determining what Palworld, modding frameworks, dependencies, and mods are actually present on the user's system and presenting that information in a useful and trustworthy way.

More advanced concepts such as guided failure isolation, structured support reports, compatibility observations, and deeper diagnostics will be developed only after the underlying diagnostic workflow has been validated.

The application is still under active development. Its interface, internal APIs, database format, diagnostic rules, and workflows may change before the first public release.

For future development plans and milestones, see [ROADMAP.md](ROADMAP.md).

---

## Screenshots

Coming soon.

---
