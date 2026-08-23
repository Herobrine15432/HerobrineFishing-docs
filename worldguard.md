# WorldGuard

WorldGuard 7.0.18 is optional and is loaded through its official API. Put region IDs in a species' `conditions.regions` list. IDs are normalized to lowercase.

When a native catch is selected, the plugin queries applicable regions once at the hook location. A species with region conditions is eligible when at least one configured ID is applicable and all other conditions pass. The central fight processor never calls WorldGuard.

Set `integrations.worldguard: false` to ignore region lookups. Without WorldGuard, region-restricted species cannot match because the captured region set is empty.

`integrations.denied-fishing-regions` is an explicit whole-catch denial list. In one of those regions the Paper event is deliberately denied, no bait is consumed, no native/custom reward is produced, and the player receives a localized message. This is different from a species `conditions.regions` mismatch, which merely removes that species and may allow another custom fish or vanilla fallback.
