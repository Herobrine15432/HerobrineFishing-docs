# Fish Species

Every species is an immutable configuration definition with an ID, display name, rarity, open string type, item template, weight model, conditions, fight values, and base market price.

The default rarity distribution is exactly:

- Common: 28
- Uncommon: 20
- Rare: 14
- Epic: 10
- Legendary: 6
- Mythic: 2

The catalog ranges from carp, perch, trout, salmon, bass, cod, reef fish, pike, sturgeon, tuna, swordfish, and sharks to distinctive high-tier species such as Moon Koi, Crystal Carp, Storm Eel, Ghost Koi, Voidfin, and Celestial Coelacanth. IDs and all definitions are in `fish.yml`.

Conditions are evaluated before bait or Luck weighting. `conditions.required-baits` may require one of the configured bait IDs, but bait never bypasses biome, depth, Y, time, weather, region, world, or rod restrictions. Fight definitions choose `FOUR` or `EIGHT` directions alongside pull, interval, and pattern. Duration normally inherits from the fish rarity; an explicit `fight.duration-seconds` overrides the rarity range for that species.
