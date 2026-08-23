# Vanilla Enchantments

HerobrineFishing does not implement a parallel enchantment simulator.

- Lure changes native Minecraft bite timing. The plugin does not add a second waiting system.
- Luck of the Sea adds to managed rod Luck when species weights are calculated, but cannot make an ineligible species eligible.
- Unbreaking controls native durability consumption.
- Mending repairs the native durability bar through Minecraft mechanics.
- Curse of Vanishing behaves natively on death.

Configured enchantments use namespaced keys such as `minecraft:lure`. Server owners should test enchantment balance on a real Paper server.

Loading or consuming bait mutates only the existing rod's signed bait PDC and the configured lore representation. It reuses the same `ItemMeta`; it does not rebuild the rod or remove enchantments. The automated preservation contract covers Lure, Luck of the Sea, Unbreaking, Mending, and Curse of Vanishing, while live Paper QA must still confirm their native server behavior.
