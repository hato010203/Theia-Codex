> This document describes the high-level architecture of Theia.
> It defines domain boundaries and responsibilities, not implementation details.

Platform
(RPG Maker MZ)

        ↓

Infrastructure
(Plugin Framework)

        ↓

Game Domains
(Character / Combat / Controls / Contents / AI)

---
THEIA

├── Character
│     ├── Appearance
│     │      ├── Body
│     │      ├── Equipment
│     │      └── Animation Style
│     │
│     ├── Stats
│     ├── Skilltree
│     └── Progression
│            ├── Level
│            ├── Weapon Mastery
│            ├── Core Skill
│            └── Awakening
│
├── Combat System
│     ├── Interfaces
│     ├── EquipmentManager
│     ├── Resolver
│     ├── Profiles
│     ├── Combat Style
│     ├── Break
│     ├── OverDrive
│     └── Weapon Identity
│
├── Controls
│     ├── Input Buffer
│     ├── Combo
│     ├── Dash
│     ├── Guard
│     ├── Parry
│     └── Sneak
│
├── AI
│     ├── NPC AI
│     ├── Combat AI
│     └── Party AI
│
├── Contents
│     ├── Exploration
│     ├── Survival
│     └── Economy
│
└── Infrastructure
      ├── Plugin Registry
      ├── Shared Utilities
      ├── Constants
      ├── Resource Cache
      ├── Debug
      └── Performance
---      
