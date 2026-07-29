# Factor Analysis – User Guide

This guide describes the workflow, interface elements, and outputs of the **Factor Analysis** module in XInsight. It serves as a companion to Factor Analysis – Tutorials, explaining the underlying interface mechanics, checks, and guidelines that the tutorials put into practice.

---

## What is Factor Analysis?

Factor Analysis is a data-reduction technique used to find a small number of underlying concepts—called **factors**—that explain the patterns and correlations among a larger set of variables. 

To make these factors easier to interpret, XInsight applies **Varimax rotation**. This aligns variables clearly with factors so that they load either very strongly or very weakly on a given factor, making them easier to identify and name.

---


### Step 1: Open Statistical Analysis
From the left navigation panel in XInsight, click on **Statistical Analysis**.

---

### Step 2: Select a Dataset
In the main panel, under the heading **Select a dataset:**, click the dropdown box and select your active dataset.

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/67c46707-3c32-4532-b1b2-5425ed0e90dd" />

---

### Step 3: Open the Factor Analysis Tab
Once a dataset is selected, XInsight displays four analysis tabs:
1. **Testing of Hypothesis**
2. **Two-Way / Multiway Table**
3. **Pivot Table**
4. **Factor Analysis**

Click on the **Factor Analysis** tab.

---

### Step 4: Review Automated Ingest Checks
As soon as you open the tab, XInsight automatically prepares your data for analysis and prints status updates directly to the screen.

#### 1. Dataset Preview
The module displays the first 10 rows of your dataset under the label `Dataset Preview (First 10 Rows)`.

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/e5d58ce6-1885-4829-9930-48037067e601" />

#### 2. Automated Ingest and Cleaning Status
XInsight automatically prepares your dataset for analysis. It checks the dataset for duplicate columns, variables with zero variance, and highly correlated or linearly dependent columns, printing the status messages directly to the screen. 

If text categories are present, XInsight automatically factorizes them into sequential numbers, renames them with a `num_` prefix, and excludes any datetime fields before running the analysis.

#### 3. Data Readiness Warning
If the dataset does not have enough numeric variables after preprocessing, a yellow warning box appears, and the analysis halts:
> `Data is not ready for Factor Analysis as there is only 1 or 0 numeric columns`

#### 4. Column Variances
If the data is ready, XInsight displays the calculated variance of each preprocessed column under a blue informational box labeled:
> `Variance of each column of dataset`

---

### Step 5: Run Suitability Checks
Before extracting factors, you must verify that the variables share enough correlation to make the analysis meaningful. XInsight provides two buttons in a blue informational box labeled:

> `Please confirm dataset is applicable for factor analysis`

Two buttons are rendered in columns: **BARTLET** (left) and **KMO** (right).

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/9476e54f-7141-41e4-ae3f-d0058d742558" />


---

#### Bartlett's Test of Sphericity (**BARTLET** Button)
Clicking this button runs a significance test to check if the variables are completely uncorrelated.
- **Output**: Prints `Chi-square: [Value], P-value: [Value]` below the button.
- **Interpretation**:
  - **p-value $\le$ 0.05**: Reject the "variables are uncorrelated" hypothesis. XInsight displays a green success box:
    > `Applicable for factor analysis`
  - **p-value > 0.05**: The variables are uncorrelated. XInsight displays a green success box:
    > `Not Applicable for factor analysis`

---

#### Kaiser-Meyer-Olkin (KMO) Test of Sampling Adequacy (**KMO** Button)
Clicking this button measures the proportion of common variance among your variables.
- **Output**: Prints `KMO: [Value]` below the button.
- **Interpretation**:
  - **KMO > 0.7**: Deemed suitable by the platform's default rule. XInsight displays a green success box:
    > `Applicable for factor analysis`
  - **KMO $\le$ 0.7**: Deemed unsuitable. XInsight displays a green success box:
    > `Not Applicable for factor analysis`

While XInsight uses a simplified `0.7` success cutoff, rely on these standard bands for interpretation:

| KMO Score | Adequacy | Recommendation |
|---|---|---|
| **0.8 or above** | Excellent / Good | Very suitable for factor extraction |
| **0.7 to 0.8** | Good | Suitable; proceed |
| **0.6 to 0.7** | Acceptable | Marginal; proceed with caution |
| **Below 0.5** | Not Recommended | Unacceptable; factors will extract noise |

---

### Step 6: Choose Extraction Mode
After suitability checks, XInsight displays a blue info bar:

> `Get Ready for Fact Analysis`

Below this header, click one of the two extraction mode buttons: **User Choice** or **Deafult** (spelled exactly this way in the user interface).

---

#### Option A: Default Mode (**Deafult** Button)
Click this button to let XInsight automatically determine the number of factors to extract using the **Kaiser Criterion** (retaining all factors with eigenvalues greater than 1).

<img width="1920" height="630" alt="image" src="https://github.com/user-attachments/assets/dd39bf9d-cebc-4ec6-b407-652c6eada114" />
<img width="1920" height="839" alt="image" src="https://github.com/user-attachments/assets/cfdcdbaa-6c2e-4162-a253-85eb7400e9c3" />
<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/820f77e9-a622-4079-a660-2bf2fcf15f76" />



##### 1. Scree Plot & Kaiser Criterion
The Scree Plot displays eigenvalues in descending order. Factors whose eigenvalues plot above the horizontal dashed line (`y=1`) are retained. XInsight counts these factors and prints:

> `Suggested number of factors used can be: [Count]`

##### 2. Default Loadings Table
XInsight fits the model with the suggested number of factors and displays the rotated loadings matrix under the text `Factor Loadings:\n`.

##### 3. Primary Feature Mapping Table
Below the loadings, XInsight displays a summary table mapping variables to factors where the loading is **greater than 0.4**.

---

#### Option B: User Choice Mode (**User Choice** Button)
Click this button to manually specify the number of factors to extract.

<img width="786" height="729" alt="image" src="https://github.com/user-attachments/assets/4ec6ce0e-a2d8-4819-8661-85fc350976f4" />



##### 1. Specify Factors
Choose a value from the selectbox dropdown: `Choose the number of factors` (supports values 1 to 6).

##### 2. Factor Variance Table
XInsight fits the model and outputs raw statistics under the label `Factor Variance`. This displays three metrics:
- **SS Loadings**: The sum of squared loadings for each factor.
- **Proportional Variance**: The proportion of total variance explained by each factor.
- **Cumulative Variance**: The running total of explained variance across factors.

##### 3. Loadings and Mapping Tables
Just like in Default Mode, XInsight renders the rotated `Factor Loadings` matrix and the primary feature mapping table (loadings $> 0.4$).

---

## Interpreting the Output Tables

### 1. Factor Loadings Table
A loading coefficient represents the correlation between a variable and an extracted factor. Because a Varimax rotation is applied, your loadings should ideally be polarized—either very close to 1 or -1 (strong relationship) or near 0 (no relationship).

Use these thresholds to interpret individual loadings:

| Loading Value | Strength | Meaning |
|---|---|---|
| **$\ge$ 0.70** | Very Strong | The variable is an excellent representative of the factor. |
| **0.50 to 0.70** | Strong | The variable has a solid relationship with the factor. |
| **0.30 to 0.50** | Moderate | The variable is moderately related; may be considered a cross-loader. |
| **Below 0.30** | Weak / Negligible | The variable does not belong to this factor. |

* **Cross-Loaders**: If a variable has moderate loadings on multiple factors (e.g., $0.45$ on Factor 1 and $0.40$ on Factor 2), it is a cross-loader. This means it is not a clean representative of a single concept.
* **Lone Variables**: If a variable does not appear in the final Feature Mapping table, its loading on all extracted factors was less than 0.4.

---

### 2. Feature Mapping Table
The final table maps each feature to its factor if its loading exceeds `0.4`. Review this table to identify the conceptual themes of your factors. 

To name your factors:
1. Look at the variables grouped under `Factor1`, `Factor2`, etc.
2. Identify their shared conceptual theme.
3. Assign a descriptive name to each factor (e.g., mapping `Staff_Friendliness`, `Response_Speed`, and `Complaint_Handling` to a factor suggests the name **Service Quality**).

---
# Factor Analysis – Tutorials

This is a companion to the [Factor Analysis User Guide](./FactorAnalysis.md). That guide walks through the mechanics of the **Factor Analysis** tab in the **Statistical Analysis** module. This page puts those mechanics into practice with three short, self-contained tutorials, each built around a small dataset you can download and follow along with.

| # | Tutorial | Dataset | What it teaches |
|---|---|---|---|
| 1 | [Customer Satisfaction Survey](#tutorial-1--customer-satisfaction-survey) | `customer_satisfaction_survey.csv` | The full happy-path workflow: suitability checks → extraction → interpretation |
| 2 | [Employee Engagement Survey](#tutorial-2--employee-engagement-survey) | `employee_engagement_survey.csv` | **User Choice vs. Default** — why forcing the wrong number of factors muddies your results |
| 3 | [Store Audit Metrics](#tutorial-3--store-audit-metrics) | `store_audit_metrics.csv` | What it looks like when a dataset **fails** the suitability checks, and what to do about it |
| 4 | [Workplace Wellbeing Survey](#tutorial-4--workplace-wellbeing-survey) | `workplace_wellbeing_survey.csv` | Passing suitability is **not enough** — what a messy, hard-to-interpret solution looks like and why it happens |
| 5 | [When Bartlett and KMO Disagree](#tutorial-5--when-bartlett-and-kmo-disagree) | `website_analytics_sessions.csv`, `pilot_training_feedback.csv` | The two suitability checks can point in **opposite directions** on the same dataset — why that happens and which one to trust |

All datasets are available alongside this guide in the `EXAMPLES/datasets/` folder.

---

## Before you start: the general workflow

Every Factor Analysis run in XInsight follows the same five moves, laid out in full in the [User Guide](./FactorAnalysis.md):

1. Open **Statistical Analysis** from the left navigation panel.
2. Under **Select a Dataset**, choose the dataset for this tutorial.
3. Open the **Factor Analysis** tab (alongside Testing of Hypothesis, Two-Way/Multiway Table, and Pivot Table).
4. Check dataset suitability using **Bartlett's Test** and the **KMO Test**.
5. Choose the number of factors (**User Choice** or **Default**), then review the **Factor Loadings Table**.

Each tutorial below picks up at step 2 and fills in the specifics.

---

## Tutorial 1 — Customer Satisfaction Survey

### Scenario

A retail chain surveys 220 customers on an 8-item, 1–7 scale questionnaire covering both how they were treated in-store and how they feel about the products themselves. The analyst suspects these 8 items really measure only two underlying things — not eight independent ones — and wants Factor Analysis to confirm that and reveal what those two things are.

### Dataset: `customer_satisfaction_survey.csv`

220 respondents, 8 numeric items (1–7 Likert scale):

---

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/d6092062-4565-4799-b641-8dbb2e130c86" />


---

### Steps in XInsight

1. Select **customer_satisfaction_survey.csv** as the active dataset.
2. Go to **Statistical Analysis → Factor Analysis**.
3. Run the suitability checks: click **Bartlett** and **KMO**.
4. Under **Choose the Number of Factors**, click **Default** — with a clean, unfamiliar dataset, let the platform find the natural structure first.
5. Review the **Factor Loadings Table**.

### Step 4: Suitability check 

---

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/360b0a27-4141-434f-9354-9ce34f9f5484" />

---

Both checks pass comfortably, so it's reasonable to move on to extraction.

### Step 5: Number of factors

With **Default** selected, the platform lands on **2 factors** — matching the two eigenvalues above 1 (≈2.73 and ≈2.45; the next-largest is only ≈0.58, a clean drop-off).

### Step 6: Factor Loadings Table 

<img width="1920" height="629" alt="image" src="https://github.com/user-attachments/assets/8beb6084-3ce2-4a30-a922-276c468e4288" />
<img width="1920" height="645" alt="image" src="https://github.com/user-attachments/assets/94b07999-d8df-4d57-b973-cc68db13d2dc" />
<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/9e58d60e-5ad7-4282-a87f-e8a27644634f" />


---

Every item loads strongly (> 0.70, "Very Strong" per the loading guide) on exactly one factor and weakly on the other — a textbook clean structure.

### Step 7: Interpreting the factors

| Factor | High-loading variables | Suggested name |
|---|---|---|
| Factor 1 | Product_Durability, Product_Design, Value_For_Money, Product_Features | **Product Quality** |
| Factor 2 | Staff_Friendliness, Response_Speed, Complaint_Handling, Store_Cleanliness | **Service Quality** |

The eight survey items collapse into two meaningful business dimensions — exactly what the analyst suspected. Instead of tracking eight separate scores, the retailer can now report on **Product Quality** and **Service Quality** as two composite indices.

> **Try it yourself:** switch to **User Choice** and force 1 factor. Watch the communalities drop and both item groups blend into a single, harder-to-interpret factor — a good demonstration of why under-extracting loses real structure.

---

## Tutorial 2 — Employee Engagement Survey

### Scenario

An HR team runs a 9-item engagement survey they *believe* covers three separate themes — trust in leadership, career growth, and work-life balance — but they're not certain the data actually supports three distinct factors. This tutorial uses **User Choice** and **Default** side by side to show why the choice matters.

### Dataset: `employee_engagement_survey.csv`

240 employees, 9 numeric items (1–7 Likert scale):

---

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/55ce7230-61a8-4d3c-a645-c1a74a8aaece" />


---

### Step 4: Suitability check 

---

<img width="1920" height="610" alt="image" src="https://github.com/user-attachments/assets/271cd02e-759f-4980-ba44-30ce6d0904b0" />

---

### Step 5a: Forcing 2 factors (User Choice)

Selecting **User Choice → 2** produces this loadings table:

---

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/bac6b8da-cc7c-47fe-a928-3eae82f1cc5d" />


---

Notice the problem: **Career Growth** items (Promotion_Opportunity, Skill_Development, Career_Path_Clarity) and **Work-Life Balance** items (Workload_Balance, Flexible_Hours, Time_Off_Support) are jammed onto the same factor, with only "Moderate" loadings (0.30–0.70) and lower communalities. Two genuinely different themes have been forced together.

### Step 5b: Using Default instead

Switching to **Default** lets the platform pick the number of factors itself. With three eigenvalues above 1 (≈2.28, ≈2.12, ≈1.89,1.00) and a sharp drop to the fourth (≈0.58), it lands on **4 factors**:

---

<img width="800" height="534" alt="image" src="https://github.com/user-attachments/assets/a3b567d7-da7d-4d9d-9019-9da68a193851" />

<img width="840" height="645" alt="image" src="https://github.com/user-attachments/assets/691230aa-b31b-4b7a-93f0-f2ebb30f0753" />
<img width="847" height="912" alt="image" src="https://github.com/user-attachments/assets/ad8e28f5-949a-464a-89f7-9676f3a9dae1" />

---

Every item now loads strongly (> 0.70) on exactly one factor, and communalities rise across the board — a much cleaner recovery of the three themes the HR team expected.


### The takeaway

**User Choice** is valuable when you have a strong, well-founded reason to fix the number of factors (a validated survey instrument, a prior study, a business requirement). Absent that, start with **Default** — the eigenvalue-based selection here recovered a cleaner, more interpretable structure than an under-specified manual choice did. If User Choice and Default disagree, treat that as a signal to look closer, not to assume the manual choice was right.

---

## Tutorial 3 — Store Audit Metrics

### Scenario

An analyst pulls six operational metrics per store — footfall, transaction value, staff count, store age, distance from the warehouse, and parking spots — and, without thinking it through, runs Factor Analysis hoping to find "hidden dimensions" of store performance. This tutorial shows what happens when the data doesn't actually contain any shared structure to find.

### Dataset: `store_audit_metrics.csv`

180 stores, 6 numeric metrics with no built-in relationship to one another:

---

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/6328b7b9-ba33-4db0-9ac1-cf4aac97bcb2" />

---

### Step 4: Suitability check

---

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/6cdcffb3-deec-4ef4-8e2d-f4a5ee4b3fef" />
<img width="805" height="254" alt="image" src="https://github.com/user-attachments/assets/ad6f0a71-1a78-415a-9926-333f00f6ae53" />


---

Both checks point the same direction: this dataset is a poor candidate for Factor Analysis.

### What to do instead of proceeding

Don't force a factor solution onto data like this — with near-zero shared correlation, any "factors" the platform extracts will be extracting noise, not real structure, and the resulting loadings and factor names would be meaningless. Options at this point:

- **Reconsider the variable set.** These six metrics may simply describe unrelated operational facts about a store rather than reflecting a small number of underlying dimensions. Factor Analysis assumes correlated variables that share common causes — not every dataset satisfies that assumption, and that's fine.
- **Check for a data or scope problem.** Low KMO can also result from including variables that don't belong together conceptually, or from too small a sample relative to the number of variables. Revisit variable selection before re-running.
- **Use a different tool for the actual question.** If the real goal is to understand which of these metrics predict store performance, a regression or correlation analysis (see **Two-Way/Multiway Table** or **Testing of Hypothesis**) is more appropriate than Factor Analysis.

> **Contrast with Tutorials 1 and 2:** both of those datasets were deliberately built from a small number of underlying themes expressed through multiple correlated survey items — exactly the setting Factor Analysis is designed for. This dataset has neither correlated items nor an underlying theme to recover, and the suitability checks correctly say so before any misleading loadings table gets produced.

---

## Tutorial 4 — Workplace Wellbeing Survey

### Scenario

An HR team runs a 9-item workplace wellbeing survey, hoping Factor Analysis will reveal a handful of clean underlying themes — the same way Tutorial 1 and Tutorial 2 did. The data passes both suitability checks without any trouble. But the resulting factor solution refuses to organize itself into clean, nameable groups. This tutorial exists because **that** outcome is common in real survey data, and it's important to recognize it rather than force an interpretation onto it.

### Dataset: `workplace_wellbeing_survey.csv`

210 employees, 9 numeric items (1–7 Likert scale), covering everything from overall job satisfaction to office comfort to team social life:

---

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/7ba80ec0-c316-4992-b733-d3f1f9e2649e" />


---

### Step 4: Suitability check

---

### Screenshot Required

<img width="815" height="257" alt="image" src="https://github.com/user-attachments/assets/93179484-2d3d-4832-9535-520d5ffab68f" />
<img width="810" height="249" alt="image" src="https://github.com/user-attachments/assets/4f640a4a-7384-4c52-be12-9f18a5f82161" />

---

This is the trap: both checks look at least as strong as Tutorial 1's, so it would be reasonable to expect an equally clean result. It doesn't arrive.

### Step 5: Number of factors — no clean elbow

---

<img width="1920" height="696" alt="image" src="https://github.com/user-attachments/assets/13627d78-8775-4502-ac24-efd809314225" />


---

Compare this to Tutorial 1, where the fourth eigenvalue (0.58) was less than a quarter of the second (2.45) — a sharp, unambiguous drop. Here, eigenvalue 3 (1.04) and eigenvalue 3 (0.92) are nearly the same size. Kaiser's rule (eigenvalue > 1) technically selects **2 factors**, but the case for stopping at 2 rather than 3 is weak — this is an early warning sign, visible before you even look at the loadings.

### Step 6: Factor Loadings Table (3 factors, Default)

---
<img width="630" height="510" alt="image" src="https://github.com/user-attachments/assets/68708654-37a5-4ba0-a413-c1554c2a6bba" />


---

### Step 7: Trying (and failing) to interpret cleanly

A few problems jump out, and they're the ones to learn to recognize:

- **Only one clean item.** Social_Events_Quality loads strongly and exclusively on Factor 2 (0.85). Nothing else in the table is that unambiguous.
- **Cross-loaders.** Team_Camaraderie (0.49 / 0.38) and Sense_Of_Belonging (0.35 / 0.46) load at similar strength on *both* factors — neither clearly "belongs" to one. Forcing them into a factor to compute a name is a coin flip, not a finding.
- **A grab-bag "Factor 1."** The items with their highest loading on Factor 1 — Overall_Job_Satisfaction, Would_Recommend_Employer, Equipment_Quality, Commute_Convenience, Manager_Approachability — don't share an obvious theme. Overall satisfaction, office equipment, and manager approachability aren't naturally "the same thing"; they just happen to be things that all correlate with feeling generally positive about work.
- **Low communalities.** Most items sit in the 0.34–0.51 range (compare to 0.57–0.71 in Tutorial 1) — meaning even the "best" 2-factor solution only explains a third to a half of most items' variance. A lot is left unaccounted for.

Trying 4 factors (available via **User Choice**) doesn't rescue this: Sense_Of_Belonging ends up nearly tied across two factors (0.53 / 0.52), and Commute_Convenience splits across two as well (0.39 / 0.47) — adding a factor produces more cross-loaders, not a cleaner picture.

### What's actually going on

This pattern — strong overall correlation, but no clean separation into distinct factors — is usually a sign of a **dominant general factor**: most items here are really tapping into one underlying "how positive do I feel about work overall" sentiment, with only faint, inconsistent traces of anything more specific underneath it. Bartlett's Test and KMO only check whether variables are correlated *at all*; they say nothing about whether those correlations organize into distinct, separable themes. A single strong general factor produces exactly this signature: excellent suitability scores, no clean elbow, moderate-everywhere loadings, and cross-loading items.

**What to do with a result like this:**

- **Don't force factor names onto weak or tied loadings.** If two items are within roughly 0.1 of each other across factors, treat the item as unclassified rather than assigning it to whichever side happens to be numerically larger.
- **Consider whether a single composite score is more honest than several factor labels.** If one dominant factor is doing most of the work, reporting "Overall Workplace Sentiment" as one index may better reflect the data than inventing two or three thinly-supported sub-themes.
- **Re-examine the item set.** Items written as broad, evaluative questions ("Overall satisfaction," "Would you recommend...") tend to load on everything and can crowd out more specific structure. A revised survey with more narrowly-scoped items per intended theme is more likely to separate cleanly on a re-run.
- **Treat this as a valid finding, not a failed analysis.** "These items mostly measure one thing" is itself useful information — it's a different, but not lesser, result than Tutorial 1's clean two-factor split.

> **Contrast with the other three tutorials:** Tutorial 3 told you *not to run* the analysis (suitability fails outright). Tutorials 1 and 2 gave you clean, confidently nameable factors. This tutorial is the middle case, and arguably the one to watch for most carefully in real data: the checks say "go ahead," the platform will happily produce a loadings table, and it's entirely possible to write confident-sounding factor names on top of a structure that isn't really there.

---

## Tutorial 5 — When Bartlett and KMO Disagree

### Scenario

Bartlett's Test and the KMO Test usually point the same direction — both green, or both red, as in Tutorials 1 and 3. Occasionally they don't. This isn't a glitch: the two tests answer genuinely different questions, so they're allowed to disagree. This tutorial covers both ways it can happen, using one dataset for each.

**Bartlett's Test** asks: *is the correlation matrix statistically distinguishable from "no correlation at all"?* It's a significance test, so — like any significance test — its result depends heavily on **sample size**, not just on how strong the correlation actually is. With enough rows, even tiny, practically meaningless correlations become "significant."

**KMO** asks a different question entirely: *of the correlation that exists, how much of it looks like shared, common-factor variance rather than noise?* It's a descriptive ratio, not a significance test, and it's mostly indifferent to sample size — it cares about whether correlation is *concentrated* in a way that supports a small number of factors, not just whether correlation exists.

Because one is about magnitude-times-sample-size and the other is about structural concentration, they can diverge in either direction.

---

### Case A: Bartlett says yes, KMO says no

**When this happens:** a large sample size combined with real, but weak and diffuse correlation — correlation that's spread thinly across many variable pairs rather than concentrated around a small number of underlying themes.

**Dataset:** `website_analytics_sessions.csv` — 12,000 browsing sessions, 10 behavioral metrics (session duration, bounce rate, scroll depth, cart additions, and so on) that are all loosely related to "how engaged was this visitor," but not in a way that cleanly separates into distinct factors.

---

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/1d6e03c7-4597-49a6-bd4e-f9655ef6a548" />


---

**Step 4 results:**

---

<img width="782" height="218" alt="image" src="https://github.com/user-attachments/assets/1aa9de0a-8cd8-4f72-b2b6-5154cfc8592b" />
<img width="814" height="235" alt="image" src="https://github.com/user-attachments/assets/71576362-e18c-4e19-8f18-5ca328496e15" />

---

The correlation here is real (average pairwise \|r\| ≈ 0.06), and with 12,000 sessions, Bartlett's Test has more than enough power to detect it. But KMO looks past "is there correlation" to "does it organize into factors" — and with correlation this thinly and evenly spread, it doesn't. Running Factor Analysis anyway would produce loadings that mostly reflect noise, dressed up as if they meant something.

**What to do:** trust KMO here. A significant Bartlett's Test on a large sample is a weak signal on its own — treat it as confirming "not literally zero correlation," not as confirming "suitable for factor analysis." When KMO disagrees with a Bartlett result driven by a very large N, KMO is the more informative check.

---

### Case B: Bartlett says no, KMO says yes

**When this happens:** a genuinely useful correlation structure, but a sample too small for Bartlett's Test to reach statistical significance.

**Dataset:** `pilot_training_feedback.csv` — an 8-item feedback survey from an 11-person pilot cohort for a new training program. Small pilot groups like this are common early in a rollout, well before a full survey wave.

---

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/f290d9cc-db43-4b14-83f8-75b3fd078d9e" />


---

**Step 4 results:**

---

<img width="813" height="233" alt="image" src="https://github.com/user-attachments/assets/ecc38fa6-0005-49eb-8aa4-e27ef8534068" />
<img width="777" height="195" alt="image" src="https://github.com/user-attachments/assets/cf98cfec-dc6d-4e6c-aa37-ad07baa4493d" />

---

The items here are genuinely correlated (average pairwise \|r\| ≈ 0.38 — a moderate, real relationship, nothing like Case A's 0.06). But with only 11 respondents, Bartlett's Test simply doesn't have the statistical power to call that significant. KMO, which isn't a significance test and doesn't need the same sample size to register a coherent pattern, picks it up anyway.

**What to do:** don't let a non-significant Bartlett result alone talk you out of proceeding, especially in a small-sample pilot context — check KMO first. If KMO is Acceptable or better despite a non-significant Bartlett, the more defensible read is "underpowered test," not "no real structure." The right long-term fix is collecting more responses before drawing firm conclusions from the factor solution, not abandoning the analysis outright.

---

### Summary: which one wins?

| Situation | What's really going on | Which check to lean on |
|---|---|---|
| Bartlett significant, KMO low, **large N** | Real but diffuse correlation; Bartlett is overpowered by sample size | **KMO** |
| Bartlett not significant, KMO acceptable+, **small N** | Real correlation; Bartlett is underpowered by sample size | **KMO** |
| Both agree | No conflict to resolve | Either |

In both directions, **KMO is the more informative check** — it's not a significance test, so it isn't distorted by sample size the way Bartlett's Test is. This doesn't mean skip Bartlett's Test entirely (a Bartlett result of "not even close to significant" on a reasonably sized sample is still a useful early warning), but when the two disagree, treat KMO as the tiebreaker rather than assuming something is wrong with the tool.

> **This is not a bug.** Both numbers are computed correctly from the same correlation matrix; they're simply designed to catch different things. Seeing them disagree occasionally is expected behavior, not a sign that XInsight has made an error.

---

## Quick reference

### KMO interpretation

| KMO Value | Result |
|---|---|
| Above 0.8 | Excellent |
| 0.7 – 0.8 | Good |
| 0.6 – 0.7 | Acceptable |
| Below 0.5 | Not Recommended |

### Factor loading interpretation

| Loading Value | Interpretation |
|---|---|
| \> 0.70 | Very Strong |
| 0.50 – 0.70 | Strong |
| 0.30 – 0.50 | Moderate |
| < 0.30 | Weak |

### Datasets used in this guide

| File | Used in | Rows | Items | KMO | Suitable? |
|---|---|---|---|---|---|
| `customer_satisfaction_survey.csv` | Tutorial 1 | 220 | 8 | 0.785 (Good) | Yes — clean 2-factor structure |
| `employee_engagement_survey.csv` | Tutorial 2 | 240 | 9 | 0.672 (Acceptable) | Yes — needs 3 factors, not 2 |
| `store_audit_metrics.csv` | Tutorial 3 | 180 | 6 | 0.490 (Not Recommended) | No — variables are unrelated |
| `workplace_wellbeing_survey.csv` | Tutorial 4 | 210 | 9 | 0.801 (Good/Excellent) | Passes checks, but **no clean factor structure** — dominant general factor |
| `website_analytics_sessions.csv` | Tutorial 5A | 12,000 | 10 | 0.472 (Not Recommended) | Bartlett significant, KMO low — large N, diffuse correlation |
| `pilot_training_feedback.csv` | Tutorial 5B | 11 | 8 | 0.594 (Acceptable) | Bartlett not significant, KMO usable — small N, real correlation |

### Common mistakes to avoid

- **Skipping the suitability check.** Bartlett's Test and KMO exist to stop you before you interpret noise as meaning — always run them first (Tutorial 3).
- **Assuming a good KMO guarantees a clean solution.** Suitability checks confirm variables are correlated, not that they separate into distinct, nameable themes — a strong KMO can still produce a diffuse, hard-to-interpret result if one dominant general factor is at play (Tutorial 4).
- **Panicking when Bartlett and KMO disagree.** They test different things and are allowed to point in different directions — check your sample size before assuming the tool is wrong (Tutorial 5).
- **Defaulting to User Choice out of habit.** Unless you have a specific, well-founded reason to fix the factor count, start with Default and let the eigenvalue structure guide you (Tutorial 2).
- **Over-interpreting weak loadings.** A loading below 0.30 tells you almost nothing about which factor an item belongs to — don't force an interpretation onto it.
- **Naming factors before checking cross-loadings.** An item with similar-sized loadings on two factors (a "cross-loader") is a warning sign that either the factor count or the item itself needs a second look, not something to gloss over when assigning names.

