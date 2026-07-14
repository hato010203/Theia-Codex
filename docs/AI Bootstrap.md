# AI Bootstrap

Read this file first before opening any other document.

---

# Project

Project Name:
Theia

Genre:
Fantasy Action RPG

Engine:
RPG Maker MZ (Prototype)
Unity (Future)

Repository Purpose:
Shared design memory between Director, Architect, Engineer and Repository AI.

---

# Philosophy

Design for longevity.

Every system must be:

- Modular
- Replaceable
- Data-driven
- Easy to extend
- Single Source of Truth

Never duplicate logic.

---

# Team Roles

Director
- Game design
- Worldbuilding
- Final decisions

Systems Architect (ChatGPT)
- Architecture
- Long-term design
- Review
- Documentation standards

Lead Engineer (Claude)
- Implementation
- Engine analysis
- Performance
- Refactoring

Repository Manager (Codex)
- Documentation
- ADR
- GitHub organization
- Knowledge preservation

---

# Current Architecture

EquipmentManager
↓

GripState

↓

Combat Resolver

↓

Combat Profile

↓

Animation Resolver

↓

Animation Profile

Everything downstream reads from these resolved profiles.

Never derive the same information twice.

---

# Core Principles

EquipmentManager
- Low-level only.
- Raw equipment access.
- No gameplay logic.

Combat Resolver
- Resolves combat state.
- Cached.
- Invalidated only by equipment or grip changes.

Animation Resolver
- Resolves animation state.
- Independent from combat mechanics.

Combat Style != Animation Style

Combat Style
= Gameplay configuration.

Animation Style
= Visual presentation.

---

# Hard Rules

Never use:

actor.weapons()

Gameplay must always use:

EquipmentManager

or

actor.equips()

because weapons() destroys slot information.

Never duplicate resolver logic.

Everything reads resolved profiles.

---

# Repository Goal

GitHub is the project's shared memory.

Architecture decisions belong here.

Never rely on chat history as the primary source of truth.

---

# Current Priority

Establish the complete equipment architecture before implementing gameplay.

Current work:

- Equipment System
- Combat Resolver
- Animation Resolver
- Combat Profile
- Animation Profile

No premature implementation.

Architecture first.
