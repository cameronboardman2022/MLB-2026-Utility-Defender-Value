# MLB 2026 Utility Defender Value — Methodology

## 1. Research Objective

This project investigates how defensive performance, positional versatility, positional difficulty, and playing time can be combined to evaluate MLB utility defenders during the 2026 season.

The primary research question is:

**Which MLB players provide the strongest combination of defensive performance and positional flexibility?**

Catchers are excluded because their defensive responsibilities require a different evaluation framework.

## 2. Data Collection

The analysis uses a dataset of 89 eligible MLB utility defenders, incorporating:

- Player identification and defensive innings
- Outs Above Average (OAA)
- Defensive positions played
- Positional playing-time distributions
- Calculated positional versatility measures

The original data provider, extraction date, and source URLs must be documented and independently verified before publication.

## 3. Defensive Performance

Defensive performance is evaluated using Outs Above Average, a Statcast-based measure of fielding performance.

To account for differences in playing time, OAA is standardized per 1,000 defensive innings:

**OAA per 1,000 innings = (Total OAA / Total defensive innings) × 1,000**

This rate facilitates comparisons between players with different defensive workloads.

## 4. Positional Versatility

The model incorporates a positional versatility score based on the distribution of defensive innings across eligible positions.

It also considers the number of positions at which a player accumulated meaningful playing time.

The exact versatility formula and minimum positional-innings threshold should be included in the final methodology.

## 5. Positional Difficulty

The model incorporates a demanding-position share component to recognize the defensive responsibilities associated with different fielding positions.

The definition of demanding positions and their relative treatment should be documented directly from the scoring code.

## 6. Composite Defensive Value Model

The model evaluates utility defenders using five normalized components: defensive performance, positional versatility, meaningful positions played, demanding-position share, and total defensive innings.

The primary balanced model assigns the following weights:

| Component | Weight |
|---|---:|
| OAA per 1,000 innings | 45% |
| Positional versatility | 25% |
| Meaningful positions | 15% |
| Demanding-position share | 10% |
| Total defensive innings | 5% |

The adjusted composite score is calculated as:

**Composite Score = 100 × (0.45 × Normalized Adjusted OAA Rate + 0.25 × Normalized Versatility + 0.15 × Normalized Meaningful Positions + 0.10 × Normalized Demanding-Position Share + 0.05 × Normalized Defensive Innings)**

The model uses min-max normalization to place components on a comparable scale.

Players are ranked in descending order of adjusted composite score.

### Alternative Weighting Scenarios

To evaluate sensitivity to model assumptions, two alternative weighting systems are applied:

**Defense-focused:** 60% OAA rate, 15% versatility, 10% meaningful positions, 10% demanding-position share, and 5% playing time.

**Versatility-focused:** 30% OAA rate, 35% versatility, 20% meaningful positions, 10% demanding-position share, and 5% playing time.

These scenarios help determine whether players maintain strong rankings when defensive performance or positional flexibility receives greater emphasis.

The composite score is a custom evaluation index, not a direct estimate of defensive runs or wins above replacement.

## 7. Sensitivity Analysis

Three alternative weighting scenarios were evaluated:

- Balanced
- Defense-first
- Versatility-first

Rankings were compared across scenarios to assess how sensitive player evaluations are to changes in model assumptions.

Ezequiel Duran ranked first in all three scenarios. Myles Straw and Sung-Mun Song also remained in the top 10 across all three.

## 8. Alternative Eligibility Analysis

An additional model comparison excluded players with nonpositive OAA rates.

Of the original top 20, 16 remained in the alternative top 20, while four new players entered.

All five original highest-ranked players retained their positions.

This analysis illustrates how eligibility decisions affect the rankings without establishing that a positive-OAA cutoff is necessarily optimal.

## 9. Data Validation

Internal quality checks covered:

- Duplicate player identifiers
- Missing required values
- Positive defensive innings
- OAA rate calculation consistency
- Composite score bounds

All five checks passed.

These checks establish internal consistency but do not independently verify the accuracy or completeness of the original data.

## 10. Limitations

The analysis has several limitations:

- OAA estimates contain measurement uncertainty.
- Small defensive samples can produce unstable rate statistics.
- Model rankings depend on subjective weighting decisions.
- Positional flexibility does not necessarily imply above-average skill at every position.
- The composite index is not calibrated directly to runs or wins.
- Independent source verification remains necessary.
- Video scouting and contextual player evaluation are outside the current model.

## 11. Conclusion

The model provides a reproducible framework for comparing defensive performance and positional flexibility among eligible MLB utility defenders.

Its primary contribution is illustrating the tradeoffs between fielding performance, positional usage, and playing time rather than claiming to produce a definitive ranking of defensive talent.