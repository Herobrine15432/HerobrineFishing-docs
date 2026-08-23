# Custom Rod

Every rod must use `FISHING_ROD`. Only Luck and Control are accepted as custom gameplay stats.

```yaml
rods:
  marsh:
    display-name: Marsh Rod
    luck: 2
    control: 4
    rarity: UNCOMMON
    allowed-types: [swamp]
    allowed-species: []
    item:
      material: FISHING_ROD
      name: '<green><bold><rod>'
      lore:
        - '<gray><rarity>'
        - '<gray>☘ <luck>'
        - '<gray>◎ <control>'
        - '<gray>Bait: <bait>'
      custom-model-data: 4100
      item-model: mypack:marsh_rod
      glint: false
      unbreakable: false
      native-rarity: UNCOMMON
      enchantments:
        minecraft:lure: 1
    shop:
      enabled: true
      price: 1200.0
```

Empty allow-lists mean unrestricted. Rod rarity controls deterministic presentation ordering. Native enchantments and native durability continue to apply when bait PDC/lore changes. After reload, give it with `/fishingadmin rod give <player> marsh`.

The official eight rods reserve CustomModelData `1001–1008`. Custom rods should use a non-colliding value and include normal and cast-state model definitions if they are added to a resource pack.
