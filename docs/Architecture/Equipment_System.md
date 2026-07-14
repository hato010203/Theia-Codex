# Equipment System

Purpose
- Foundation of combat architecture.

Pipeline
Equipment
→ EquipmentManager
→ GripState
→ CombatResolver
→ CombatProfile
→ AnimationResolver
→ AnimationProfile
→ SpriteLayer

Rules
- Equipment never controls gameplay.
- Resolver computes.
- Profile stores.
- Manager provides.
- SpriteLayer reads AnimationProfile only.

Dependencies
CombatResolver
AnimationResolver
EquipmentManager

Status
Stable Design
