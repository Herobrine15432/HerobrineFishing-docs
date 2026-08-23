# Admin Guide

Run `/fishingadmin` as a player to open the 54-slot control center. It links to Fish, Rods, Baits, Players, Shop, Market, Active Fights, Configuration, Reload, and Reset submenus. Fish is rarity-sorted and paginated; selecting any species opens the shared Fish Detail view even if player details are disabled or the viewing admin has not discovered it. The admin-only panel adds ID, material, CustomModelData, base price, pattern, duration, and pull. Back returns to the same list page. Active fights show player, fish, rarity, remaining seconds, exact anchor center, and current direction. Console administrators use `/fishingadmin help [page]`.

Use give commands for testing or rewards; generated fish receive a unique catch UUID, rods a unique physical identity, and bait an authenticated signature. Bait list/info/give/inspect and shop status/enable/disable are console-compatible. Profile and stats read the in-memory cache loaded from SQLite.

`/fishingadmin nextfish <online-player> <fish|clear|status>` provides a silent one-shot test encounter under `herobrinefishing.admin.nextfish`. It bypasses normal random-selection eligibility but never managed-rod, lifecycle, passenger/dead/Spectator, WorldGuard explicit deny, or session-commit safety. It is not stored in SQLite and clears after the forced fight commits, explicit clear, disconnect, or plugin disable.

Always test configuration changes on staging. A failed reload leaves the previous snapshot active. Global resets require uppercase `CONFIRM` and create a database snapshot.
