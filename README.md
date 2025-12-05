# Eniac A/B Test Analysis

## Project Overview
This repository contains the analysis of an A/B test conducted on Eniac’s homepage to evaluate the effectiveness of different call-to-action buttons. The goal was to improve user engagement and conversion by testing variations of the “SHOP NOW” and “SEE DEALS” buttons.

## Experiment Design

**Tested Variants:**

| Version | Button Text  | Color |
|---------|-------------|-------|
| A       | SHOP NOW    | White |
| B       | SHOP NOW    | Red   |
| C       | SEE DEALS   | White |
| D       | SEE DEALS   | Red   |

**Hypotheses:**

- **Null Hypothesis (H0):** All button variants have the same click-through rate (CTR).  
- **Alternative Hypothesis (H1):** At least one variant has a different CTR.

**Metrics Tracked:**

1. **Click-Through Rate (CTR):** Clicks on the button divided by total homepage visits.  
2. **Drop-Off Rate:** Percentage of users who initiate a conversion process but do not complete it.  
3. **Homepage-Return Rate:** Measures how often users return to the homepage after clicking the button.

**Statistical Significance:**

- Confidence Level: 95%  
- Minimum Detectable Effect (MDE): 20%  
- Post-hoc tests used Bonferroni adjustment to account for multiple comparisons.

## Data

The CSV files for each variant are stored in the `data/` folder:

```text
data/
├─ eniac_a.csv
├─ eniac_b.csv
├─ eniac_c.csv
└─ eniac_d.csv
```
Each CSV contains the number of clicks and total visits, along with metadata for analysis.

## Analysis

The analysis was performed using Python with the following workflow:

1. Load the CSV files into DataFrames.  
2. Calculate **clicks** and **non-clicks** for each variant.  
3. Create a contingency table and perform a **Chi-Square test** to check for statistical significance.  
4. Perform **post-hoc tests** with Bonferroni adjustment to compare each pair of variants.  
5. Compute CTRs and identify top-performing contenders.

### Key Findings

- Versions A (White SHOP NOW) and C (White SEE DEALS) performed better than B and D.  
- However, the comparison between A and C was inconclusive.  
- No single variant emerged as a clear winner based on CTR alone.

## Next Steps / Observations

Since there was no single winning variant:

- Consider **another experiment** focused on the top contenders (A and C).  
- Analyze **additional metrics** such as drop-off rate and homepage-return rate to inform decision-making.  
- Use these secondary metrics as **tiebreakers** to choose the final variant.
