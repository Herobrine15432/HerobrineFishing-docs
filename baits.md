# Baits

The defaults are Worm, Insect, Cricket, Shrimp, Squid, Minnow, Golden Bait, and Abyssal Bait. They primarily change which already-eligible fish are more likely to be selected. A bait can modestly shift generated weight, and selected species may require a bait ID. Bait never bypasses environment, rod, region, time, weather, Y, or water-depth conditions.

Hold an authenticated HerobrineFishing rod and **Left Click Air while idle** to open the 27-slot Bait Loader. Left Click Block is untouched. A cast/waiting bobber, active custom fight, passenger state, another plugin GUI, or the brief hook-removal lifecycle transition blocks opening. The 400ms transition guard distinguishes Paper's reel/catch `LEFT_CLICK_AIR` from a later deliberate click, so cleanup never opens the menu but normal use remains responsive.

Only the center Bait Slot is special. Left/right cursor insertion, partial removal, same-bait stack merging, and shift-click from the lower inventory are supported. A different bait type is never swapped automatically: remove the loaded bait first. Invalid shift-clicked items stay where they are, decorative slots remain protected, and ordinary lower-inventory clicks/movement pass through. Number/offhand actions that could move the bound rod, top-inventory drags, and double-click collection are blocked for transaction safety.

The session binds player UUID and the rod's signed unique UUID. It revalidates that exact rod in either hand on every mutation; moving, swapping, removing, or dropping that rod closes safely. Every accepted mutation is serialized immediately to `loaded_bait_type` and `loaded_bait_amount` on the physical rod. The center is only a mirror, so close, forced close, death, disconnect, reload, and disable cannot leave a second authoritative bait stack.

Exactly one bait is consumed after a custom species is selected and its fight session successfully starts. Cast, WorldGuard/passenger denial, vanilla fallback, no eligible fish, and failed session creation consume none. Once committed, leaving the anchor, death, disconnect, teleport/world change, passenger entry, rod invalidation, manual cancellation, and every other escape do **not** refund it. Catch or escape cleanup never consumes a second item.

## Custom bait

Add one unique lower-case ID under `baits:` in `baits.yml`. Configure display name, shared item fields (material, lore, custom model data, item model, glint, enchantments, flags, native rarity), maximum stack size, rarity, effect description, fish/type/rarity multipliers, modest minimum/maximum weight multipliers, and `shop.enabled`/`shop.price`. Fish/type references, stack bounds, finite positive prices/modifiers, and safe weight ranges are validated transactionally.
