# PalForge Roadmap

This document describes the long-term development roadmap of PalForge.

Unlike the CHANGELOG, which records completed work, this roadmap defines the planned direction of the project from early development to the first stable release.

---

# Project Status

| Item            | Status                              |
| --------------- | ----------------------------------- |
| Stage           | Alpha                               |
| Current Version | Alpha 0.1.2                         |
| Current Phase   | Phase 4 — Modern User Interface     |
| Last Updated    | 2026-08-11                          |

---

# Development Principles

PalForge follows several core principles throughout development.

- Architecture comes before new features.
- New functionality should extend the existing architecture instead of bypassing it.
- Business logic should remain independent from the user interface whenever possible.
- User-facing text should not be hardcoded into application logic.
- PalForge should avoid silently guessing when an installation decision is uncertain.
- Existing files should be protected before PalForge replaces them.
- Completed modules should not be rewritten unless required for maintenance, migration, bug fixes, or major architectural improvements.
- Major completed milestones should be documented in CHANGELOG.md and reflected in ROADMAP.md.

---

# Phase 0 — Foundation

**Status:** ✅ Completed

## Objective

Build the initial PalForge prototype and establish the core local mod workflow.

## Major Goals

- Project initialization
- ZIP archive scanning
- ZIP structure detection
- Local mod database
- SHA-256 archive matching
- Manual Identify workflow
- Basic mod installation
- Backup system
- Initial CurseForge provider groundwork

---

# Phase 1 — Core Architecture

**Status:** ✅ Completed

## Objective

Transform the prototype into a modular application that can grow without tying core functionality to a specific interface.

## Major Goals

- Separate Core modules
- Introduce Models
- Introduce Providers
- Introduce Controllers
- Introduce Services
- Create a unified error hierarchy
- Introduce the localization system
- Improve project structure

---

# Phase 2 — UI Decoupling

**Status:** ✅ Completed

## Objective

Separate business logic from the user interface and prepare PalForge for migration to a new UI framework.

## Major Goals

- Move application logic into Controllers
- Introduce DatabaseService
- Standardize controller result models
- Remove Tkinter dependencies from Core
- Remove Tkinter dependencies from Controllers
- Remove Tkinter dependencies from Services
- Make the UI responsible primarily for presentation

## Completion Criteria

- Core contains no Tkinter code
- Controllers contain no Tkinter code
- Services contain no Tkinter code
- Models contain no Tkinter code
- Business logic can be reused by another UI framework

---

# Phase 3 — PySide6 Migration

**Status:** ✅ Completed

## Objective

Replace the legacy Tkinter interface with PySide6 / Qt and restore the complete local mod workflow on the new interface.

## Major Goals

- Introduce PySide6
- Create the Qt application entry point
- Create the Qt main window
- Migrate archive scanning
- Migrate mod installation
- Migrate the Identify workflow
- Integrate installed mod inspection
- Add installation conflict handling
- Add Replace and Skip Existing behavior
- Integrate automatic backups
- Add mod type overrides
- Add editable saved identities
- Integrate localization into the Qt interface
- Add first-launch language selection
- Add persistent language preferences
- Add runtime language switching
- Remove the remaining Tkinter implementation
- Clean up obsolete migration and legacy files

## Completion Criteria

- Qt is the default PalForge interface
- Tkinter implementation is removed
- Archive scanning works through the Qt interface
- Identify works through the Qt interface
- Supported mods can be installed through the Qt interface
- Existing installation targets can be handled safely
- Installed mods can be inspected
- English and Traditional Chinese interfaces are functional
- User-facing UI text is routed through the localization system
- Existing architecture remains separated from the UI framework

---

# Phase 4 — Modern User Interface

**Status:** 🚧 Current

## Objective

Transform the functional Qt interface into the modern PalForge user experience intended for public use.

The current interface proves that the underlying workflow works. Phase 4 focuses on how users interact with that functionality.

## Major Goals

- Redesign the main application layout
- Introduce sidebar navigation
- Introduce the Project view
- Introduce the Browse view
- Redesign Installed Mods management
- Reduce unnecessary buttons and move secondary actions into menus
- Introduce toast notifications for non-blocking feedback
- Reserve dialogs for decisions that require user input
- Add progress indicators for longer operations
- Improve installation and conflict dialogs
- Improve responsive resizing
- Improve visual hierarchy and spacing
- Add application icons and UI assets
- Improve accessibility
- Add theme support
- Prepare the interface for future provider integration

---

# Phase 5 — Feature Expansion

**Status:** ⏳ Planned

## Objective

Expand PalForge from a local mod installer into a more complete mod management platform.

## Major Goals

- CurseForge integration
- Mod browsing and discovery
- Direct mod downloads
- Dependency handling
- Automatic dependency installation
- Mod update detection
- Mod update management
- Improved conflict management
- Improved installed mod management
- Version compatibility checking
- Additional mod providers
- Steam and Game Pass platform handling
- Dedicated Server support
- Profiles and mod collections
- Additional quality-of-life improvements

---

# Phase 6 — Stable Release

**Status:** ⏳ Planned

## Objective

Prepare PalForge for its first stable public release.

## Major Goals

- Complete user documentation
- Complete developer documentation
- Stable application packaging
- GitHub Releases
- Application update system
- Crash reporting
- Performance optimization
- Final UI polish
- Installation and upgrade testing
- Version 1.0.0 release

---

# Future Vision

After Version 1.0.0, PalForge may expand beyond its initial scope.

Potential future areas include:

- Additional mod providers
- Plugin and extension support
- Extended mod metadata
- Cloud synchronization
- Community-driven integrations
- Additional game support

These items are long-term possibilities rather than committed features.

---

# Documentation Policy

PalForge maintains separate documents for different purposes.

| Document     | Purpose                                           |
| ------------ | ------------------------------------------------- |
| README.md    | What PalForge is and what it currently supports   |
| CHANGELOG.md | Changes completed in each released version        |
| ROADMAP.md   | Development direction and project milestones      |
