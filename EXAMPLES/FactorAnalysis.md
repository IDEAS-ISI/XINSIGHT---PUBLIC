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

