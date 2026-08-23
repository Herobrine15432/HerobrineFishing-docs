# Fishing Shop

`/fishing shop` opens a small category menu, then separate paginated Fishing Rods and Baits pages. The shop never sells fish. Rod and bait entries are rarity-first and display concise gameplay values, effect text, and the current configured price.

The YAML defaults are `shop.enabled: true`, `shop.rods.enabled: true`, and `shop.baits.enabled: true`. Individual rod/bait definitions also require `shop.enabled: true` and a positive finite price. `/fishingadmin shop status|enable|disable` stores a persistent global override in `shop-state.properties`; that override takes precedence over the YAML global default without rewriting owner formatting. Category and definition switches continue to apply.

Vault plus a registered compatible economy provider is required only for purchases. Without it, fishing and the Bait Loader continue normally and the GUI explains that economy is unavailable.

Left Click buys one item. Shift + Left Click buys 16 bait, capped to that bait's configured maximum stack size. A purchase resolves the current definition/price at click time, checks full capacity and finite balance, withdraws exactly once, and delivers exactly once. It never partially delivers or charges a full inventory. Claimed menu actions and a per-player transaction guard stop duplicate clicks; a rare capacity change after withdrawal triggers a refund attempt.

