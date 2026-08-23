# Weight

Each species defines positive `minimum`, `maximum`, and a `distribution` of `NORMAL` or `UNIFORM`. Both algorithms are bounded, so an awarded or marketable fish can never fall outside the exact configured range.

UNIFORM gives equal density across the interval. NORMAL averages three uniform values to create a bounded center-weighted curve without clamp spikes.

Market price is:

```text
basePrice × (1 + normalizedWeight × maximumWeightBonus)
```

where normalized weight is 0 at the minimum and 1 at the maximum. Prices are rounded to two decimals.

