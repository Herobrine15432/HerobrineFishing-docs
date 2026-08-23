# Market

The market is intentionally simple. It has no stock, demand simulation, timers, or dynamic history. An authenticated fish's price depends only on its configured base price and normalized exact weight.

The GUI reads fish from the player's storage slots. A click revalidates the slot, signed species, exact weight bounds, unique catch UUID, and signature. Sell All builds one validated plan and makes one Vault deposit. Menu session IDs, claimed action IDs, and catch UUIDs prevent stale or rapid duplicate clicks.

If Vault or an economy provider is missing, the market reports unavailable and every non-market feature continues to work.

The market is distinct from the Fishing Shop: players sell authenticated caught fish here; fish are never sold by the shop. Market entries use the same deterministic rarity-first catalog ordering.
