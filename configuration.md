# Configuration

Runtime configuration is intentionally limited:

- `config.yml`: prefix/debug, exact anchor half-width/margin, per-rarity telegraphs, EASY/NORMAL/HARD/CUSTOM fight profiles, collection-detail toggle, visuals, shop/category defaults, sorting, storage, and integrations
- `fish.yml`: defaults and species
- `rods.yml`: defaults and rods
- `baits.yml`: item templates, rarity, selection/weight modifiers, stack limit, effect text, and shop price
- `rarities.yml`: six rarities, rarity-level fight duration ranges, and configurable type IDs
- `gui.yml`: titles, materials, icon templates, and GUI presentation
- `languages/en.yml`
- `languages/it.yml`

`plugin.yml` is packaged metadata, not owner configuration.

Reload parsing builds a complete immutable candidate and validates IDs, fish/rod/bait references, finite numeric ranges and prices, materials, rarities, stack limits, modifiers, GUI icons, and exact EN/IT scalar parity. Only a valid candidate is atomically activated. A fish requiring a missing bait rejects the candidate. Changing `storage.database-file` requires a restart.

The admin shop toggle is stored in `shop-state.properties`, not YAML. Its persistent runtime value overrides `config.yml`'s `shop.enabled`; the `shop.rods.enabled` and `shop.baits.enabled` category switches still apply. Delete that properties file while stopped to return to the YAML default.

Fight duration resolution is `species fight.duration-seconds` (or legacy `duration-ticks`) → `rarities.<RARITY>.fight.duration` → `fish.yml defaults.fight`. Rarity ranges use finite positive `minimum-seconds` and `maximum-seconds`, with maximum at least minimum. The technical validation ceiling is 86,400 seconds (24 hours), so 30- and 60-second encounters are fully supported. The shipped ranges are Common 6–8, Uncommon 8–11, Rare 11–15, Epic 15–20, Legendary 20–25, and Mythic 25–30 seconds. Species inherit these rather than duplicating 80 final values.

```yaml
rarities:
  MYTHIC:
    fight:
      duration:
        minimum-seconds: 25
        maximum-seconds: 30
```

Pull strength, interval, pattern, direction set, `fight.anchor.half-width`, margin, grace, safety velocity cap, bounded weight bonus, per-rarity telegraph milliseconds, and difficulty multipliers remain data-driven and reload transactionally. `collection.fish-details.enabled: false` disables only player detail opening; administrative inspection remains available.
