# Factor Analysis – User Guide

This guide explains how to use the **Factor Analysis** feature in the **Statistical Analysis** module.

---

## Step 1: Open Statistical Analysis

1. From the left navigation panel, click **Statistical Analysis**.
2. The **Statistical Analysis** workspace will open.

```markdown
![Statistical Analysis Module](images/statistical_analysis.png)
```
<img width="1824" height="618" alt="Screenshot 2026-06-18 133718" src="https://github.com/user-attachments/assets/6714d5bf-453d-4edd-ae7e-b6ca5cc3e437" />

---

## Step 2: Select a Dataset

1. At the top of the page, locate the **Select a Dataset** dropdown.
2. Click the dropdown and choose the dataset you want to analyze.
3. Once selected, the system displays a preview of the first 10 rows of the dataset.

```markdown
![Dataset Selection](images/dataset_selection.png)
```

---

## Step 3: Open the Factor Analysis Tab

1. In the **Statistical Analysis** section, locate the available analysis tabs:

   * Testing of Hypothesis
   * Two-Way / Multiway Table
   * Pivot Table
   * Factor Analysis

2. Click **Factor Analysis**.

The Factor Analysis page will load.

```markdown
![Factor Analysis Tab](images/factor_analysis_tab.png)
```
<img width="1841" height="793" alt="Screenshot 2026-06-18 133617" src="https://github.com/user-attachments/assets/d4fd249b-07ee-4e53-943c-68ab1ec2465e" />

---

## Step 4: Check Dataset Suitability

The system automatically evaluates whether the selected dataset is suitable for Factor Analysis.

### Bartlett's Test

Click **Bartlett** (if required by the platform).

The system calculates:

* Chi-square Value
* P-value

### KMO Test

Click **KMO** (if required by the platform).

The system calculates the **KMO Score**.

### KMO Interpretation

| KMO Value | Result          |
| --------- | --------------- |
| Above 0.8 | Excellent       |
| 0.7 – 0.8 | Good            |
| 0.6 – 0.7 | Acceptable      |
| Below 0.5 | Not Recommended |

> A KMO value above **0.5** indicates that Factor Analysis can be performed.

```markdown
![KMO and Bartlett Test Results](images/kmo_bartlett_results.png)
```
<img width="1834" height="579" alt="Screenshot 2026-06-18 133815" src="https://github.com/user-attachments/assets/eda5e83f-ff3f-4a76-86e2-82b0153f8099" />

---

## Step 5: Choose the Number of Factors

The platform provides two options for selecting the number of factors.

### Option 1: User Choice

1. Click **User Choice**.
2. Select the desired number of factors from the dropdown.

#### Example

```text
Number of Factors = 4
```

Use this option when you already know how many factors you want to extract.

```markdown
![User Selected Factors](images/user_choice_factors.png)
```
<img width="1862" height="765" alt="Screenshot 2026-06-18 133911" src="https://github.com/user-attachments/assets/0ff648e1-30bf-4908-8781-c444d6d74cab" />

---

### Option 2: Default

1. Click **Default**.
2. The platform automatically determines the optimal number of factors.

Use this option if you are unsure how many factors should be used.

```markdown
![Default Factor Selection](images/default_factor_selection.png)
```
<img width="1857" height="726" alt="Screenshot 2026-06-18 134002" src="https://github.com/user-attachments/assets/bcde422f-8c1e-497e-a785-a244d94224a3" />

---

## Step 6: Review Factor Loadings

The platform displays the **Factor Loadings Table**.

Factor loadings indicate how strongly each variable is associated with a factor.

### General Guidelines

| Loading Value | Interpretation |
| ------------- | -------------- |
| > 0.70        | Very Strong    |
| 0.50 – 0.70   | Strong         |
| 0.30 – 0.50   | Moderate       |
| < 0.30        | Weak           |

### Recommendation

Focus on variables with the highest loading values for each factor.

```markdown
![Factor Loadings Table](images/factor_loadings.png)
```

---

## Step 7: Interpret the Factors

Analyze the variables grouped under each factor.

### Example

| Factor   | Variables                 |
| -------- | ------------------------- |
| Factor 1 | Money, Hour of Day        |
| Factor 2 | Month, Date               |
| Factor 3 | Product-related Variables |

Based on the variables with high loadings, assign a meaningful business name to each factor.

### Example Factor Names

* Sales Activity
* Time-Based Trends
* Seasonal Behavior
* Customer Preferences

```markdown
![Factor Interpretation](images/factor_interpretation.png)
```

---

## Summary

The Factor Analysis module helps identify hidden patterns and relationships among variables by grouping them into factors. Before performing the analysis, the platform evaluates dataset suitability using Bartlett's Test and the KMO Test. Users can either specify the number of factors manually or allow the system to determine them automatically. The resulting factor loadings help users interpret and label factors for meaningful business insights.



