Equipment System

Goal
Combat foundation.

Flow
Equipment
→ Manager
→ Grip
→ CombatResolver
→ CombatProfile
→ AnimationResolver
→ AnimationProfile

Rules
Manager = data
Resolver = compute
Profile = immutable result

Invalidation
Equip
Grip

Never
actor.weapons()
