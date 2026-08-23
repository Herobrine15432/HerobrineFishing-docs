# Resource Pack

The customer release includes the optional `HerobrineFishing-ResourcePack-26.2.zip`: 80 fish textures, 8 rod textures, and 8 bait textures. The game remains fully functional without it and falls back to configured vanilla materials.

Official CustomModelData ranges are fish `3001–3080`, rods `1001–1008`, and bait `2001–2008`. Internal JAR defaults and `default-config/` are synchronized to those mappings. See the top-level `RESOURCE-PACK.md` for client/server installation and verified SHA-1/SHA-256 hashes.

Item templates support both a numeric custom model data component and the modern namespaced item-model key. Owners may use either or both according to their resource-pack format.

- `custom-model-data: 3100`
- `item-model: mypack:twilight_trout`

Keep keys namespaced and validate them with `/fishingadmin reload`. Fish, rods, and bait all share these template fields. Names, lore, material, glint, unbreakable state, native item rarity, flags, and enchantments remain independently configurable. PDC identity and HMAC signatures do not depend on the visible model, so cosmetic resource-pack changes do not invalidate legitimate items.
