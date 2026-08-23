# Reset System

Player categories are `collection`, `stats`, and `all`. Global categories are the same. Resets affect SQLite/cache data only; they never scan playerdata, delete physical items, or alter Vault balances.

A global reset:

1. closes active fights,
2. closes the profile mutation gate,
3. flushes dirty profiles asynchronously,
4. checkpoints SQLite WAL,
5. creates a timestamped consistent database snapshot in `reset-snapshots/`,
6. verifies database integrity,
7. applies the selected category in one transaction,
8. rebuilds the relevant cache state, and
9. reopens mutations.

Without the final uppercase `CONFIRM`, no global mutation occurs. YAML, the plugin JAR, and unrelated server data are preserved.

