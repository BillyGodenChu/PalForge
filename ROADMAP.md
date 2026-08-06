# PalForge Roadmap

This document describes the long-term development roadmap of PalForge.

Unlike the CHANGELOG, which records completed work, this roadmap defines the planned direction of the project from early development to the first stable release.

---

# Project Status

| Item | Status |
|------|--------|
| Stage | Alpha |
| Current Version | Alpha 0.1.1 |
| Current Phase | Phase 3 — PySide6 Migration |
| Last Updated | 2026-08-07 |

---

# Development Principles

PalForge follows several core principles throughout development.

- Architecture comes before new features.
- New functionality should extend the existing architecture instead of bypassing it.
- Completed modules should not be rewritten unless required for maintenance, migration, bug fixes, or major architectural improvements.
- Business logic should remain independent from the user interface whenever possible.
- Every completed milestone should be documented in both CHANGELOG.md and ROADMAP.md.

---

# Phase 0 — Foundation

**Status:** ✅ Completed

## Objective

Build the initial prototype and establish the project's basic functionality.

## Major Goals

- Project initialization
- ZIP archive scanning
- ZIP structure detection
- Local mod database
- SHA-256 archive matching
- Manual Identify workflow
- Basic installer
- Backup system
- CurseForge API integration

---

# Phase 1 — Core Architecture

**Status:** ✅ Completed

## Objective

Transform the prototype into a modular application.

## Major Goals

- Separate Core modules
- Introduce Models
- Introduce Providers
- Introduce Controllers
- Introduce Services
- Create unified error hierarchy
- Introduce localization system
- Improve project structure

---

# Phase 2 — UI Decoupling

**Status:** ✅ Completed

## Objective

Separate business logic from the user interface.

## Major Goals

- Move application logic into Controllers
- Introduce DatabaseService
- Standardize controller result models
- Remove Tkinter dependencies from Core
- Remove Tkinter dependencies from Controllers
- Remove Tkinter dependencies from Services
- Make the UI responsible only for presentation

## Completion Criteria

- Core contains no Tkinter code
- Controllers contain no Tkinter code
- Services contain no Tkinter code
- Models contain no Tkinter code
- Business logic is reusable by any future UI framework

---

# Phase 3 — PySide6 Migration

**Status:** ⏳ Planned

## Objective

Replace the legacy Tkinter interface with a modern Qt interface while keeping the existing application architecture unchanged.

## Major Goals

- Introduce PySide6
- Create the Qt application entry point
- Create the main window
- Migrate Scan UI
- Migrate Install UI
- Migrate Identify workflow
- Migrate CurseForge interface
- Remove the remaining Tkinter implementation

## Completion Criteria

- Qt becomes the default interface
- Tkinter implementation is fully removed
- Existing Controllers require little or no modification
- Existing Services require no modification
- Existing Core modules require no modification

---

# Phase 4 — Modern User Interface

**Status:** ⏳ Planned

## Objective

Provide a modern desktop experience comparable to contemporary game launchers and mod managers.

## Major Goals

- Modern layouts
- Sidebar navigation
- Toast notifications
- Progress indicators
- Better dialogs
- Responsive resizing
- Theme support
- Improved icons
- Better accessibility

---

# Phase 5 — Feature Expansion

**Status:** ⏳ Planned

## Objective

Expand PalForge beyond its initial feature set.

## Major Goals

- Automatic dependency installation
- Automatic update detection
- Better conflict management
- Additional mod providers
- Improved database management
- Better version compatibility checking
- Additional quality-of-life improvements

---

# Phase 6 — Stable Release

**Status:** ⏳ Planned

## Objective

Prepare PalForge for its first stable public release.

## Major Goals

- Complete documentation
- Stable installer
- GitHub Releases
- Automatic updates
- Crash reporting
- Performance optimization
- Final UI polish
- Version 1.0.0 release

---

# Future Vision

After Version 1.0.0, development may continue in the following areas.

- Additional mod providers
- Plugin system
- Extended metadata support
- Cloud synchronization
- Additional game support
- Community-driven improvements

---

# Documentation Policy

PalForge maintains separate documents for different purposes.

| Document | Purpose |
|----------|---------|
| README.md | Project introduction and user documentation |
| CHANGELOG.md | Completed changes for each released version |
| ROADMAP.md | Long-term development plan and project milestones |
