# Rarity & Types

The six fixed rarities are Common, Uncommon, Rare, Epic, Legendary, and Mythic. `rarities.yml` configures each display name, color, base selection weight, and luck scaling. All six must exist.

Fish types are not a Java enum. They are configurable IDs under `types:` in `rarities.yml`, so owners may add a type without rebuilding the plugin. Defaults are freshwater, river, lake, ocean, tropical, cold_water, swamp, deep_sea, and special.

A rod can allow zero or more type IDs. An empty allow-list means every configured type. Unknown type references fail validation before reload activation.

