# Performance

All active fights are processed by one repeating task every two ticks. The same processor handles bounded anchor markers, direction telegraphs, edge warnings, impulses, BossBars, and completion. No fight or particle task is created per player.

The fight tick performs no YAML parsing, SQLite work, Vault operation, or WorldGuard query. Environment and region conditions are captured before selection. Profiles live in memory; dirty snapshots are batched to one dedicated SQLite executor and WAL mode is enabled.

GUI pages create only the visible 45-entry slice after deterministic rarity sorting. Market and shop validation are synchronous because they must match live inventory and perform one economy transaction. Bait is rod PDC and is never duplicated in SQLite.
