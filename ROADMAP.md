# PalForge Roadmap

This document describes the long-term development roadmap of PalForge.

Unlike the CHANGELOG, which records completed work, this roadmap defines the planned direction of the project from early development toward a stable public release.

PalForge originally began as a local Palworld mod manager. After completing the core mod-management foundation, the project direction was reevaluated.

PalForge is now being developed primarily as a **diagnostics and testing toolkit for Palworld modding**, focused on understanding modded environments, assisting troubleshooting, and producing useful diagnostic information for mod users and authors.

---

# Project Status

| Item            | Status                                      |
| --------------- | ------------------------------------------- |
| Stage           | Alpha                                       |
| Current Version | Alpha 0.1.2                                 |
| Current Phase   | Phase 4 — Diagnostics Foundation            |
| Last Updated    | 2026-09-06                                  |

---

# Development Principles

PalForge follows several core principles throughout development.

- Architecture comes before new features.
- New functionality should extend the existing architecture instead of bypassing it.
- Business logic should remain independent from the user interface whenever possible.
- User-facing text should not be hardcoded into application logic.
- PalForge should avoid silently guessing when diagnostic evidence is uncertain.
- Diagnostic findings should distinguish confirmed facts from potential problems.
- PalForge should inspect the environment that actually exists rather than assuming all mods were installed through PalForge.
- PalForge should remain independent of any single mod distribution platform.
- Troubleshooting should be reproducible whenever possible.
- Diagnostic collection should avoid unnecessary personal information.
- Existing files should be protected before PalForge replaces or modifies them.
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

# Product Redefinition — Redefining What PalForge Is For

**Status:** ✅ Direction Established

After completing Phase 3, development was paused to reevaluate the long-term purpose of PalForge.

The original roadmap focused on expanding PalForge into a complete mod-management platform with mod discovery, provider integrations, direct downloads, automatic updates, and other features already provided by established platforms such as Steam Workshop, CurseForge, Nexus Mods, and Vortex.

Continuing in that direction would place PalForge in direct competition with platforms that already have significant distribution and ecosystem advantages.

The project therefore adopted a new direction.

PalForge will continue to retain its existing local mod-management capabilities, but installation and distribution will no longer define the primary purpose of the project.

The new focus is:

**Inspect → Diagnose → Isolate → Report**

PalForge aims to understand the complete modded Palworld environment regardless of where individual mods were obtained or how they were installed.

The primary target users are:

- Mod authors
- Heavy mod users
- Troubleshooters
- Server administrators
- Users managing complex or mixed-source mod environments

This direction will be validated through real-world use before larger feature expansion.

---

# Phase 4 — Diagnostics Foundation

**Status:** 🚧 Current

## Objective

Build and validate the first diagnostic workflow for PalForge.

Phase 4 focuses on determining whether PalForge can reliably inspect a real Palworld installation and present information that is useful when troubleshooting mod-related problems.

The first priority is not automatic repair.

The first priority is understanding the environment accurately.

## Major Goals

### Environment Inspection

- Detect the Palworld installation and platform
- Detect the installed game version when available
- Inspect known Palworld mod locations
- Discover installed mods regardless of whether PalForge installed them
- Detect UE4SS installations
- Detect PalSchema installations
- Detect known framework and dependency locations
- Detect manual and managed mod installations where identifiable
- Detect duplicate framework installations
- Detect legacy loader files and installation residue
- Detect unexpected or suspicious mod locations
- Build a structured environment snapshot

### Environment Health

- Introduce diagnostic findings with severity levels
- Distinguish confirmed problems from potential problems
- Detect known invalid or suspicious framework configurations
- Detect missing dependencies when they can be determined reliably
- Detect duplicate mod installations when identifiable
- Detect mixed installation environments
- Explain why a finding may matter
- Avoid automatically declaring compatibility failures without sufficient evidence

### Diagnostic Interface

- Present environment information clearly
- Separate facts, warnings, and unresolved information
- Allow users to inspect detected paths and files
- Allow diagnostic results to be refreshed
- Provide enough information for troubleshooting without overwhelming ordinary users
- Integrate all new user-facing text with the localization system

## Validation Goals

Phase 4 should answer:

- Can PalForge accurately describe a real modded Palworld installation?
- Can it identify common environment problems that currently require manual inspection?
- Does the information save users time during troubleshooting?
- Do mod authors consider the diagnostic output useful?

Phase 4 should be validated with real modded environments before the project commits to more advanced diagnostic features.

## Completion Criteria

- PalForge can produce a structured environment scan
- Installed frameworks and major mod locations can be identified
- Known duplicate or legacy framework states can be detected
- Diagnostic findings distinguish facts from suspicions
- Results are understandable through the Qt interface
- Diagnostic behavior is covered by testable Core / Service logic rather than UI-specific implementation
- Initial feedback has been collected from real Palworld mod users or authors

---

# Phase 5 — Troubleshooting and Reproduction

**Status:** ⏳ Planned

## Objective

Extend environment inspection into a structured troubleshooting workflow.

Phase 5 should help users narrow down failures without requiring them to manually track every test configuration.

## Major Goals

### Guided Failure Isolation

- Create diagnostic sessions
- Record enabled and disabled mod states
- Record whether a failure was reproduced
- Preserve test history
- Suggest the next useful test set
- Support divide-and-test strategies where appropriate
- Handle inconclusive test results
- Avoid assuming that every failure has a single-mod cause

### Environment Snapshots

- Save diagnostic environment snapshots
- Compare working and broken environments
- Highlight relevant changes between snapshots
- Track framework, dependency, configuration, and mod changes
- Support reproducible test configurations where practical

### Log and Crash Collection

- Locate relevant UE4SS logs
- Locate relevant Palworld crash information
- Extract useful diagnostic metadata
- Associate logs and crashes with diagnostic sessions
- Avoid collecting unrelated or unnecessary user data

## Completion Criteria

- A user can create and complete a diagnostic session
- PalForge can preserve the state and outcome of each test
- Working and failing environments can be compared
- Relevant logs and crash information can be associated with a test
- Diagnostic results remain evidence-based and reproducible

---

# Phase 6 — Diagnostic Reports and Author Support

**Status:** ⏳ Planned

## Objective

Turn PalForge diagnostic information into useful support material that can be shared with mod authors and troubleshooting communities.

## Major Goals

### Diagnostic Reports

- Generate human-readable diagnostic reports
- Generate structured machine-readable diagnostic data
- Include game and platform information
- Include framework and dependency information
- Include active mod manifests
- Include installation sources when identifiable
- Include diagnostic findings
- Include relevant test results
- Include selected logs and crash information

### Support Bundles

- Export portable diagnostic bundles
- Clearly preview what information will be exported
- Exclude unnecessary personal information
- Redact sensitive path information where appropriate
- Allow users to choose optional diagnostic files
- Preserve hashes and metadata useful for reproduction

### Mod Author Workflow

- Design reports around information mod authors actually request
- Reduce repeated troubleshooting questions
- Make reports easy to attach to Nexus Mods, CurseForge, GitHub, Discord, or other support channels
- Explore a stable diagnostic report format that third-party tools may consume

## Validation Goals

The most important validation question for this phase is:

**Would mod authors ask users to provide a PalForge diagnostic report when reporting a problem?**

If the answer is consistently no, the report workflow should be reevaluated before further expansion.

---

# Phase 7 — Advanced Diagnostics

**Status:** 🔬 Exploratory

## Objective

Explore deeper diagnostic capabilities only after the core diagnostic workflow has demonstrated real-world value.

Potential areas include:

- Dependency graph analysis
- Deeper configuration analysis
- Compatibility observations
- Community-tested compatibility information
- Mod interaction analysis
- Load-order analysis where applicable
- Additional framework diagnostics
- Dedicated Server diagnostics
- Steam and Game Pass environment differences
- Integration with specialized compatibility tools
- Optional automated repair for narrowly defined and well-understood problems

These features are exploratory and are not commitments.

PalForge should prefer reliable evidence over increasingly complex automation.

---

# Phase 8 — Stable Release

**Status:** ⏳ Planned

## Objective

Prepare PalForge for its first stable public release after the diagnostic direction has been validated.

## Major Goals

- Complete user documentation
- Complete developer documentation
- Stable application packaging
- GitHub Releases
- Application update system
- Crash reporting for PalForge itself
- Performance optimization
- Final UI and accessibility polish
- Installation and upgrade testing
- Diagnostic rule testing
- Version 1.0.0 release

---

# Deferred and Non-Core Areas

The following areas are intentionally not current development priorities:

- Built-in mod discovery
- Competing with Steam Workshop, CurseForge, or Nexus Mods as a distribution platform
- Direct third-party mod redistribution
- Building a general-purpose replacement for Vortex
- Automatic dependency downloading as a primary workflow
- Provider-specific browsing interfaces
- Large-scale UI redesign before the diagnostic workflow is validated
- Automatic conflict repair without sufficient evidence

Existing installation and local mod-management features will remain part of PalForge where useful, but they are considered supporting capabilities rather than the project's primary direction.

---

# Future Vision

If the diagnostic direction proves useful to the Palworld modding community, PalForge may eventually expand into a broader mod development and troubleshooting toolkit.

Potential future areas include:

- Mod author testing workflows
- Reproducible test profiles
- Community compatibility observations
- Diagnostic integrations with other modding tools
- Plugin and extension support
- Dedicated Server tooling
- Additional platform support
- Additional game support

These items are long-term possibilities rather than committed features.

---

# Documentation Policy

PalForge maintains separate documents for different purposes.

| Document     | Purpose                                         |
| ------------ | ----------------------------------------------- |
| README.md    | What PalForge is and what it currently supports |
| CHANGELOG.md | Changes completed in each released version      |
| ROADMAP.md   | Development direction and project milestones    |
