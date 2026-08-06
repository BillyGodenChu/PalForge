# Changelog

All notable changes to PalForge will be documented in this file.

The format is based on Keep a Changelog and adapted for the PalForge release cycle.

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
