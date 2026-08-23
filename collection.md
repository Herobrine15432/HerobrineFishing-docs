# Collection

A successful fight records the species, catch count, and personal best weight in SQLite. The 54-slot collection GUI reserves slots 0–44 for content and 45–53 for navigation and filters.

Filters include all species, cycling rarity, cycling configured type, discovered, and undiscovered. Pagination is calculated from the current filtered list and supports catalogs of arbitrary size.

The filtered list is sorted before pagination with the central rarity comparator: Common, Uncommon, Rare, Epic, Legendary, Mythic, then alphabetical display name. `gui.rarity-sort: DESCENDING` reverses only the rarity tier order and keeps ties deterministic.

Discovery can also be managed with `/fishingadmin collection discover|undiscover <player> <fish>`. Collection reset does not remove physical fish from inventories.

Catch a species once, then left-click its discovered entry to open Fish Detail. The same configured fish item is featured at the top, so its official resource-pack model appears automatically. The view shows rarity/type, personal catches and best weight, configured weight range, and the fully resolved rods, worlds, biomes, depth, Y, time, weather, WorldGuard regions, and required bait. Empty restrictions are shown as **Any**. Locked entries never expose these conditions.

`collection.fish-details.enabled` defaults to `true`. Disabling it leaves collection entries visible but non-interactive. Admin Fish always opens the shared detail renderer regardless of this toggle and adds ID, material, CustomModelData, price, pattern, duration, and pull strength. Back returns to the exact player page/filter or admin page.
