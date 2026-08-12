# Two-Way / Multiway Table Guide (Statistical Analysis Section)

Use this guide to build contingency tables and test for association in
**Statistical Analysis -> Two-Way / Multiway Table**.

---

## 1. Open Two-Way / Multiway Table

1. Open the app.
2. Go to **Statistical Analysis**.
3. Select your dataset.
4. Open the **Two-Way / Multiway Table** tab.

> 📸 *Screenshot placeholder: the Statistical Analysis tab bar with Two-Way / Multiway Table selected.*

---

## 2. Review the Dataset Preview and Categorical Columns

1. The first 10 rows of your dataset are shown automatically.
2. The platform automatically detects which columns are **categorical** —
   either columns already stored as text/category, or numeric columns with
   10 or fewer unique values (e.g. a 1–5 rating scale).
3. If a column you need isn't picked up automatically, use **Select columns
   to force convert to categorical (if required)** to add it manually.

> 📸 *Screenshot placeholder: dataset preview + the force-convert-to-categorical multiselect.*

**Note:** at least 2 categorical variables are required to build a
contingency table. If your dataset doesn't have that many, you'll see an
error message here instead of the variable selectors below.

---

## 3. Select Response and Explanatory Variables

1. Choose your **Response Variable** — the outcome you're interested in.
2. Choose one or more **Explanatory Variables**:
   - **1 variable** gives a standard **two-way table**.
   - **2 or more variables** gives a **multiway table**, with each row
     representing a combination of explanatory-variable categories.
3. Click **Generate Table**.

> 📸 *Screenshot placeholder: Response Variable and Explanatory Variables selectors.*

---

## 4. Review the Cross-Tabulation

The **Multiway Cross Tabulation** shows a count for every combination of
Explanatory Variable categories (rows) against Response Variable categories
(columns) — a standard contingency table.

> 📸 *Screenshot placeholder: the generated cross-tabulation table.*

---

## 5. Chi-Square Test of Association

This runs automatically once the table is generated — no extra click needed.

1. **Chi-square statistic**, **degrees of freedom**, and **p-value** are
   shown as headline metrics.
2. Below that: the hypotheses being tested and the conclusion at the 5%
   significance level.
3. **Cramér's V** — an effect-size score alongside the p-value, labeled
   negligible / small / medium / large.
4. If more than 20% of the table's expected cell counts are below 5, a
   warning appears — the chi-square approximation becomes unreliable at that
   point, and Fisher's exact test (below) is the better choice if your table
   is 2×2.
5. Expand **Show expected frequencies (under independence)** to see what the
   table would look like if the two variables had no relationship at all.

### Cramér's V Interpretation

| Cramér's V | Interpretation |
| --- | --- |
| ≥ 0.5 (2×2 tables) / ≥ 0.35 (larger) | Large |
| ≥ 0.3 (2×2) / ≥ 0.21 (larger) | Medium |
| ≥ 0.1 (2×2) / ≥ 0.07 (larger) | Small |
| Below that | Negligible |

> The exact thresholds shift slightly with table size — a 2×2 table and a
> 4×5 table don't use the same cutoffs for "strong."

> 📸 *Screenshot placeholder: the chi-square results block with metrics and Cramér's V.*

---

## 6. Fisher's Exact Test (2×2 tables only)

This section only appears when your generated table is exactly **2 rows ×
2 columns**. For any other table size, you'll see a note explaining it's
unavailable rather than an attempted (and misleading) result.

1. Choose an **Alternative Hypothesis**: Two Sided (≠), Greater Than (>), or
   Less Than (<).
2. Review the **Odds Ratio** and **P-value**.
3. Read the hypothesis statement and conclusion underneath.

Use Fisher's exact test instead of (or alongside) the chi-square result when
your sample is small or expected cell counts are low — it computes an exact
probability rather than relying on chi-square's large-sample approximation.

> 📸 *Screenshot placeholder: Fisher's exact test section with the alternative-hypothesis dropdown.*

---

## 7. How to Read the Result

Focus on:

- **Chi-square p-value** — is there an association at all?
- **Cramér's V** — if there is, how strong is it?
- **Fisher's exact p-value** (2×2 only) — a more reliable check when sample
  sizes are small.

Interpretation rule:

- If the p-value is below your chosen significance level (typically 0.05),
  reject the null hypothesis of independence — the variables are associated.
- Otherwise, fail to reject — there's no significant evidence of an
  association in this data.

---

## Summary

The Two-Way / Multiway Table module builds contingency tables across one or
more categorical variables and automatically tests whether the variables are
associated. Every generated table gets a chi-square test of independence and
a Cramér's V effect size; 2×2 tables additionally get Fisher's exact test, the
more reliable option at small sample sizes. Use the cross-tabulation to see
*where* the data concentrates, and the statistical tests to confirm *whether*
that pattern is more than chance.
