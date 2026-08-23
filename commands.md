# Commands

## Player

- `/fishing`
- `/fishing collection`
- `/fishing market`
- `/fishing shop`
- `/fishing rods`
- `/fishing stats`
- `/fishing help`
- `/fish` is the safe alias.

## Administration

- `/fishingadmin`
- `/fishingadmin help [page]`
- `/fishingadmin reload`
- `/fishingadmin fish list`
- `/fishingadmin fish info <fish>`
- `/fishingadmin fish give <player> <fish> [amount] [weight]`
- `/fishingadmin rod list`
- `/fishingadmin rod info <rod>`
- `/fishingadmin rod give <player> <rod> [amount]`
- `/fishingadmin rod inspect`
- `/fishingadmin bait list [page]`
- `/fishingadmin bait info <bait>`
- `/fishingadmin bait give <player> <bait> [amount]`
- `/fishingadmin bait inspect`
- `/fishingadmin shop status`
- `/fishingadmin shop enable`
- `/fishingadmin shop disable`
- `/fishingadmin profile <player>`
- `/fishingadmin collection discover|undiscover <player> <fish>`
- `/fishingadmin stats <player>`
- `/fishingadmin nextfish <player> <fish>`
- `/fishingadmin nextfish <player> clear`
- `/fishingadmin nextfish <player> status`
- `/fishingadmin reset player <player> [collection|stats|all]`
- `/fishingadmin reset global collection|stats|all CONFIRM`

A global reset first prints the exact repeat command ending in uppercase `CONFIRM`.

`nextfish` is an online-player, in-memory, silent-to-target, one-shot control. It bypasses random selection probability and ordinary biome, depth, time, weather, rod species/type, required-bait, rarity, and Luck eligibility, then uses the species' normal configured weight generation. It does not bypass managed-rod validity, dead/Spectator/passenger safety, fishing lifecycle, WorldGuard explicit deny, or session creation. Failed/denied attempts retain the override; a committed custom fight, explicit `clear`, target disconnect, or plugin disable clears it. Loaded bait is still consumed normally at fight commit.

`/fishing collection` opens the filterable catalog; left-clicking a discovered fish opens its detail view when enabled. In the admin GUI, Fish entries always open the same detail view with an additional technical panel. Hold a managed rod and Left Click Air while no bobber/fight is active to open Bait Loader; this is an interaction, not an extra command.
