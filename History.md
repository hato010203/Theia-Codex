# Theia Project History

This document records major architectural decisions.

Purpose:

- Preserve design reasoning.
- Prevent repeated discussions.
- Help new AI recover project context quickly.

This is NOT a meeting log.

Only important decisions belong here.

---

# Phase 0 — Project Philosophy

## Memory = Soul

The project follows a core philosophical rule:

Memory and identity are inseparable.

This principle influences both worldbuilding and development.

GitHub exists as the project's persistent memory.

---

# Phase 1 — Equipment Architecture

## Decision

Shields are implemented as Weapons instead of Armors.

All playable characters permanently use Dual Wield slots.

Right Hand = Slot 0

Left Hand = Slot 1

## Reason

This keeps RPG Maker MZ's native Weapon validation intact.

Avoids overriding canEquip() and equipSlots().

Allows:

- Shields
- Torches
- Spellbooks
- Other handheld tools

to share the same equipment model.

## Impact

Equipment becomes hand-oriented instead of Weapon/Armor-oriented.

Future systems read hand sockets rather than database categories.

---

# Phase 2 — Equipment Layer

## Decision

EquipmentManager becomes the only low-level equipment API.

Gameplay must never read actor.weapons().

## Reason

actor.weapons() removes empty slots and destroys hand information.

EquipmentManager preserves physical hand positions.

## Impact

Every gameplay system accesses equipment through EquipmentManager.

---

# Phase 3 — Combat Resolution

## Decision

Combat Resolver introduced.

## Reason

Multiple systems required the same derived information.

Without a Resolver each system would duplicate logic.

## Impact

Combat Profile becomes the Single Source of Truth.

Combat

UI

Animation

Sprite

AI

all consume the same resolved data.

---

# Phase 4 — Animation Separation

## Decision

Combat Style and Animation Style are independent systems.

## Reason

Gameplay progression and animation production evolve at different speeds.

Combat functionality must never depend on animation availability.

## Impact

Animation Resolver introduced.

Animation Profile becomes independent from Combat Profile.

Placeholder animations remain valid.

Animation upgrades require no gameplay changes.

---

# Phase 5 — Character Identity

## Decision

Dominant Hand is permanent.

Primary/Support are derived from Dominant Hand.

Off-Hand Proficiency improves over time.

## Reason

Characters gain unique identities.

Allows:

- Left-handed characters
- Ambidextrous growth
- Mechanical arms
- Special passive hands

without changing equipment architecture.

---

# Phase 6 — Combat Growth

## Decision

Weapon mastery grows through successful combat actions.

Not through enemy kills.

## Reason

Encourages growth during difficult encounters.

Progress depends on participation instead of victory.

---

# Phase 7 — Awakening

## Decision

Hidden skills are unlocked by fulfilling specific combat situations.

Not by level requirements.

## Reason

Encourages experimentation.

Connects gameplay with worldbuilding.

Rewards memorable moments instead of grinding.

---

# Current Direction

Current development priority:

Complete the entire equipment architecture before implementing gameplay.

Current focus:

- Equipment System
- Combat Resolver
- Animation Resolver
- Combat Profile
- Animation Profile
