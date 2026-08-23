# Fishing Rods

The defaults are Beginner, River, Lake, Ocean, Deep Sea, Lucky, Hunter, and Master Angler rods. Every one is a real Minecraft `FISHING_ROD`.

The only custom stats are:

- Luck: contributes to eligible species weighting.
- Control: reduces horizontal pull strength, subject to a non-zero lower bound.

Rods may restrict allowed fish type IDs and/or species IDs. Material, name, lore, custom model data, item model, glint, unbreakable flag, enchantments, and native item rarity are configurable. Durability remains Minecraft durability; there is no secondary integrity value.

Every managed rod has a signed unique identity plus `loaded_bait_type` and `loaded_bait_amount` PDC. Bait therefore follows the rod through storage, drops, and trading. Updating bait mutates the existing item metadata and configured lore placeholders; it does not reconstruct the rod, so Lure, Luck of the Sea, Unbreaking, Mending, Curse of Vanishing, models, flags, and other intended metadata remain intact.

Rod definitions also include rarity, `shop.enabled`, and a positive finite shop price. The shared lore placeholders are `<rarity>`, `<luck>`, `<control>`, and `<bait>`.
