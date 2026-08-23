# Custom Fish

Add an entry under `fish:`. The type must exist in `rarities.yml`; IDs use lowercase letters, numbers, underscores, or hyphens.

```yaml
fish:
  twilight_trout:
    display-name: 'Twilight Trout'
    rarity: RARE
    type: river
    item:
      material: SALMON
      name: '<aqua><bold><fish>'
      custom-model-data: 3100
      item-model: mypack:twilight_trout
      glint: true
      native-rarity: RARE
      enchantments: {}
    weight:
      minimum: 1.25
      maximum: 8.50
      distribution: NORMAL
    conditions:
      rods: [river, master]
      worlds: [world]
      biomes: [minecraft:river]
      minimum-y: 40
      maximum-y: 90
      minimum-depth: 2
      maximum-depth: 20
      times: [night]
      weather: [CLEAR]
      regions: []
      required-baits: [worm]
    fight:
      duration-seconds: 32
      pull-strength: 0.27
      direction-interval-ticks: 13
      pattern: ERRATIC
      directions: EIGHT
    base-price: 42.0
```

Then mirror any new localization keys, run reload, and inspect with `/fishingadmin fish info twilight_trout`.

The official catalog reserves fish CustomModelData `3001–3080` in its shipped order. Use a non-colliding value such as `3100` for additions and provide matching model, texture, and modern item-definition entries in your own pack. Omit `duration-seconds` to inherit the rarity range; an explicit value overrides rarity and global fallback. Pull strength, direction interval, pattern, and direction set remain independently configurable per species; the Fish Detail GUI always displays resolved values.
