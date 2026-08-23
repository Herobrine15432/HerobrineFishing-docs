# Fish Conditions

Conditions are ANDed. Empty lists mean unrestricted.

- `rods`: managed rod IDs
- `worlds`: case-insensitive world names
- `biomes`: namespaced biome keys such as `minecraft:frozen_ocean`
- `minimum-y` / `maximum-y`: hook Y range
- `minimum-depth` / `maximum-depth`: consecutive water blocks below the hook
- `times`: `day` and/or `night`
- `weather`: `CLEAR`, `RAIN`, and/or `THUNDER`
- `regions`: WorldGuard region IDs
- `required-baits`: one of these authenticated bait IDs must be loaded

The environment and applicable region IDs are captured once before selection. No condition or WorldGuard lookup runs in the fight tick. Bait modifiers and Luck are applied only after every environment, bait requirement, and rod restriction passes.
