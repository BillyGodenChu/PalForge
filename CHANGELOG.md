# Changelog

All notable changes to PalForge will be documented in this file.

The format is based on Keep a Changelog and adapted for the PalForge release cycle.

---

# Redefining What PalForge Is For

After completing the initial local mod-management foundation, PalForge's long-term direction was reevaluated.

The original plan was to expand PalForge into a more complete Palworld mod-management platform, including mod discovery, provider integrations, direct downloads, automatic updates, dependency management, and other quality-of-life features.

However, many of these problems are already addressed by established platforms such as Steam Workshop, CurseForge, Nexus Mods, and Vortex. Continuing in that direction would increasingly place PalForge in direct competition with platforms that already have significant distribution, ecosystem, and integration advantages.

Rather than attempting to replace those platforms, PalForge will focus on a different problem:

**Understanding what is actually happening inside a modded Palworld environment when something goes wrong.**

The project's new direction is centered around:

**Inspect → Diagnose → Isolate → Report**

PalForge will evolve toward a diagnostics and testing toolkit capable of inspecting real Palworld mod environments regardless of whether mods were installed through Steam Workshop, CurseForge, Nexus Mods, Vortex, manually, or through PalForge itself.

Existing work is not being discarded.

The archive scanner, mod detection system, local identity database, installer, backup system, installed-mod inspection, controller/service architecture, Qt interface, and localization system remain part of PalForge. These systems will provide the foundation for the new diagnostic workflow.

## Project Direction

- Shifted PalForge's primary focus from general-purpose mod management to mod diagnostics, testing, and troubleshooting.
- Repositioned installation and local mod management as supporting capabilities rather than the primary purpose of the application.
- Established environment inspection as the first priority of the new development direction.
- Planned future work around environment health checks, guided failure isolation, reproducible troubleshooting, and diagnostic reports.
- Adopted a source-independent approach: PalForge should inspect the environment that actually exists rather than requiring mods to have been installed through PalForge.
- Deferred large-scale UI expansion and provider-oriented features until the diagnostic workflow has demonstrated real-world value.
- Established mod authors, heavy mod users, troubleshooters, and complex mod environments as the primary users for validating the new direction.

## Documentation

- Reworked `README.md` to describe PalForge as a diagnostics and testing toolkit.
- Reworked `ROADMAP.md` to document the product redefinition and replace the previous mod-manager expansion plan with the new diagnostics roadmap.
- Preserved the existing development history and completed Phase 0–3 work rather than rewriting earlier milestones around the new direction.

---

# Alpha 0.1.2

> Qt migration and core mod management update.

### Added

- Added the new PySide6 / Qt desktop interface.
- Added full mod installation support to the Qt interface.
- Added installed mod detection and the **Installed Mods** viewer.
- Added installation conflict detection for existing files and folders.
- Added **Replace**, **Skip Existing**, and **Cancel** conflict handling.
- Added automatic backups before replacing existing mod files.
- Added editable identities for mods already registered in the local database.
- Added manual mod type overrides for automatically detected mods.
- Added source page actions for identified mods.
- Added first-launch language selection.
- Added runtime language switching and persistent language preferences.
- Added English and Traditional Chinese localization.
- Added localized UI text, dialogs, tooltips, logs, detection reasons, confidence levels, and structured errors.

### Changed

- Migrated the primary PalForge interface from Tkinter to PySide6 / Qt.
- Integrated scanning, identification, installation, and installed-mod inspection into the Qt application.
- Improved the Identify workflow and automatically uses the archive filename when no custom mod name is provided.
- Improved handling of database-confirmed mod types and manual overrides.
- Improved installation result handling by moving routine success and failure information into the application log instead of displaying unnecessary result dialogs.
- Improved game directory validation and path handling.
- Refactored user-facing text to use localization keys instead of hardcoded strings.
- Refactored configuration and error handling to better support localization.
- Cleaned up legacy and unused project files left from earlier development stages.

### Fixed

- Fixed duplicate installation targets being copied without proper conflict handling.
- Fixed installation conflicts not allowing existing files to be skipped.
- Fixed several Qt controller integration issues.
- Fixed Installed Mods not being connected to the main interface.
- Fixed duplicated and inconsistent UI strings introduced during the Qt migration.
- Fixed remaining hardcoded user-facing messages across the current interface.
- Fixed several legacy code paths and compatibility leftovers from the Tkinter implementation.
- 
# Alpha 0.1.1

> Architecture update.

## Added

### Controllers

- ScanController
- InstallController
- IdentifyController
- PathController

### Services

- Structured database service
- Database compatibility adapter
- Scan result model
- Install result model
- Identify result model

---

## Changed

### Architecture

- Database operations are now handled through DatabaseService.
- Scan workflow is now executed through ScanController.
- Install workflow is now executed through InstallController.
- Identify workflow is now executed through IdentifyController.
- Path handling is now managed through PathController.
- Legacy database access now uses compatibility adapters.

### User Interface

- Tkinter now acts primarily as the presentation layer.
- UI delegates business logic to controllers instead of executing it directly.
- Reduced direct coupling between the UI and application logic.

---

## Refactored

- Introduced structured database models.
- Unified controller communication.
- Standardized controller return models.
- Removed Tkinter dependencies from core application modules.
- Simplified the responsibility of `tk_main_window.py`.
- Improved project modularity for future UI migration.

---

## Fixed

- Improved controller error handling.
- Improved database serialization compatibility.
- Fixed several legacy controller integration issues.

---

# Alpha 0.1.0

> Initial public development build.

## Added

### Core

- Renamed the project to **PalForge**
- ZIP structure detection
- Local mod database
- SHA256 hash matching
- Automatic backup before overwrite
- Windows EXE build script

### CurseForge

- CurseForge API integration
- CurseForge project search
- Project version selection
- Exact file selection
- Exact file download
- Project details panel
- Open CurseForge project page
- Dependency parser
- Dependency resolver
- Provider abstraction layer

### Dependency System

- Unified dependency model
- CurseForge dependency support
- Database dependency support
- Archive structure dependency detection
- Dependency confidence system
- Dependency merge service
- Provider ↔ Database matching

### Localization

- Localization system
- English language pack
- Localization keys
- UI localization preparation

### Architecture

- Core / Model / Provider separation
- Initial Controller architecture
- Unified application error hierarchy
- Installer error hierarchy
- Provider error hierarchy
- Database error hierarchy
- Download duplicate detection
- Modular project structure

### User Interface

- CurseForge search window
- Version selection dialog
- Project details panel
- Download workflow
- Browser integration

---

## Changed

- Manual Learn was redesigned as a database enrichment feature.
- UI language is now English by default.
- Began moving business logic out of `PalForge.py`.
- Started separating UI from application logic.

---

## Fixed

- CurseForge API authentication issues
- Dependency resolution issues
- Duplicate download handling
- LogicMod enum mismatch
- Multiple CurseForge integration bugs
- Search UI integration issues

---

## Known Issues

- Tkinter UI is still under heavy development.
- Controller migration is not yet complete.
- Automatic dependency installation is not yet implemented.
- Qt-based interface is planned for a future release.
