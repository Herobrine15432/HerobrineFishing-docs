# Fishing Gameplay

The gameplay sequence is deliberately short:

1. A player casts a managed fishing rod through the native Minecraft mechanic.
2. Minecraft controls the bobber, splash, bite timing, Lure, and rod enchantment behavior.
3. At `CAUGHT_FISH`, HerobrineFishing captures world, biome, Y, water depth, time, weather, and applicable WorldGuard region IDs once.
4. Species environment, rod, region, and required-bait conditions are applied.
5. Loaded bait modifiers and then configured/native Luck adjust only the weights of remaining eligible species.
6. A weight is generated inside the species' exact range.
7. The custom session starts and exactly one loaded bait is committed; only then is Paper's pending native item suppressed.
8. The runtime next-fish override, if any, clears only at that committed boundary.

Managed custom fishing is explicitly denied while `Player.isInsideVehicle()` is true. Entering any vehicle or mount during the active physical fight causes an immediate escape; the bait was already committed and is not refunded. Unmanaged vanilla rods are not intercepted by this rule.
8. Success awards one signed fish item and updates collection/statistics. Escape awards nothing.

Plain rods never enter this pipeline and retain the complete vanilla result.

When no custom species is eligible, preparation fails, or a session cannot start, Paper's native catch is left intact. A hook UUID guard prevents a second `CAUGHT_FISH` callback from resolving again. `FAILED_ATTEMPT` and `REEL_IN` provide localized timing feedback. Enable `debug.fishing-events` for concise state/decision diagnostics.

Fights use a central impulse loop: direction telegraph, one bounded velocity impulse, recovery, then the next telegraph. Common and Uncommon fish use four cardinal directions; Rare mixes cardinal-only and eight-direction species; Epic and above use all eight.

The ActionBar arrow shows the direction you should move to counter the pull, relative to where you are currently looking. It is recalculated throughout the telegraph, so turning your camera also rotates the instruction. The anchor is a virtual square centered on your exact X/Z position at fight start, not the Minecraft block grid.
