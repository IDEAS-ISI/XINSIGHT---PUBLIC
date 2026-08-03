# Tutorial 1: One-Sample Mean Test

## Objective

This tutorial demonstrates how to perform a **One-Sample Mean Test** in XInsight. The test is used to determine whether the mean of a sample differs significantly from a known or hypothesized population mean.

---

## Learning Scenario

A school claims that the **average score of students is 75 marks**.

You have collected the scores of 10 students and would like to verify whether the true average score is significantly different from 75 using XInsight.

---

## Dataset

Create a CSV file named **exam_scores.csv** with the following data.

| Student_ID | Score |
|------------|------:|
| 1 | 72 |
| 2 | 78 |
| 3 | 81 |
| 4 | 69 |
| 5 | 74 |
| 6 | 77 |
| 7 | 80 |
| 8 | 71 |
| 9 | 76 |
| 10 | 79 |

Save the file as **exam_scores.csv**.

---

## Hypotheses

**Null Hypothesis (H₀)**

The population mean score is **75**.

**H₀: μ = 75**

**Alternative Hypothesis (H₁)**

The population mean score is **not equal to 75**.

**H₁: μ ≠ 75**

---

# Step 1: Open XInsight

Launch the XInsight application.

After opening the application, you should see the home screen.

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/5c79ef04-9d40-4757-916e-15ed663a88ce" />
---

# Step 2: Upload the Dataset

1. Click **Browse files**.
2. Select **exam_scores.csv**.
3. Click **Upload dataset**.

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/6e6ad3b3-359f-4a7a-86fb-896c221b35e8" />
---

# Step 3: Navigate to Testing of Hypothesis

From the left sidebar,

```
Statistical Analysis
    └── Testing of Hypothesis
```

Open the **Testing of Hypothesis** module.

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/f3d382ba-815d-4c07-8ac4-1e252d5c18ab" />
---

# Step 4: Go to "Tests for Mean"

Select the following options.

| Field | Value |
|----------|--------|
| Select Sample Type | One Sample |
| Select Target Variable | Score |
| Variance Type | Unknown |
| Enter Hypothesized Mean | 75 |
| Select Alternative Hypothesis | Two Sided (≠) |

After entering all parameters, verify the values once.
<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/82d18cf2-2dc4-4254-8437-3b4afbf27000" />
---

# Step 6: Run the Test

Click the **Run Test** button.

XInsight will automatically calculate

- Test Statistic
- Critical Value
- Conclusion
for different Significance Level(%)
<img width="1607" height="398" alt="image" src="https://github.com/user-attachments/assets/5a1c3114-f4e6-4b37-bf79-01709c1c0113" />
---
# Tutorial 2: Two-Sample Mean Test

## Objective

This tutorial demonstrates how to compare the means of two independent samples using the **Two-Sample Mean Test** in XInsight.

---

## Learning Scenario

An e-commerce company uses two courier services:

- **ExpressX**
- **SpeedGo**

The company wants to determine whether the average delivery time differs significantly between the two courier services.

---

## Dataset

Use **courier_delivery.csv**.

| ExpressX | SpeedGo |
|----------:|---------:|
| 3.2 | 4.1 |
| 3.5 | 4.3 |
| 3.8 | 4.5 |
| 3.1 | 4.2 |
| 3.6 | 4.6 |
| 3.7 | 4.4 |
| 3.4 | 4.7 |
| 3.3 | 4.3 |
| 3.5 | 4.5 |
| 3.6 | 4.4 |

Each column represents an independent sample of delivery times.

---

## Hypotheses

**Null Hypothesis (H₀):**

The average delivery time of ExpressX is equal to the average delivery time of SpeedGo.

**H₀: μ₁ = μ₂**

**Alternative Hypothesis (H₁):**

The average delivery times of the two courier companies are different.

**H₁: μ₁ ≠ μ₂**

---

# Step 1: Upload the Dataset

Upload **courier_delivery.csv**.

# Step 2: Open Tests for Mean
Navigate to:

**Statistical Analysis → Testing of Hypothesis → Tests for Mean**

# Step 3: Configure the Test

Select the following options.

| Field | Value |
|-------|-------|
| Select Sample Type | Two Sample |
| Select Variable 1 | ExpressX |
| Select Variable 2 | SpeedGo |
| Variance Type | Variance Unknown |
| Hypothesized Mean (μ₀) | 0 |
| Alternative Hypothesis | Two Sided (≠) |

> **Screenshot 4**
<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/f97fd979-e431-4e82-9043-3494fd58c98f" />

---

# Step 5: Run the Test

Click **Run Test**.

# Step 6: View Results

XInsight displays:
- Test Statistic
- Critical Value
- Conclusion
for different Significance Level(%)

<img width="1619" height="387" alt="image" src="https://github.com/user-attachments/assets/9cff2260-162f-4f2e-9db3-88d2580caca0" />
---
# Tutorial 3: Paired Sample Mean Test

## Objective

This tutorial demonstrates how to perform a **Paired Sample Mean Test** in XInsight. A paired sample test is used when two observations are collected from the **same subjects** before and after an intervention.

---

## Learning Scenario

A fitness center introduces an **8-week weight loss program** for its members.

To evaluate the effectiveness of the program, the weights of 10 participants are recorded:

- **Before** starting the program
- **After** completing the program

Since both measurements are taken from the **same participants**, a **Paired Sample Mean Test** is appropriate.

---

## Dataset

Use **weight_before_after.csv**.

| Before | After |
|---------:|------:|
| 82 | 79 |
| 76 | 74 |
| 91 | 87 |
| 85 | 82 |
| 79 | 77 |
| 88 | 84 |
| 95 | 91 |
| 81 | 79 |
| 87 | 84 |
| 90 | 86 |

Each row represents the weight (in kilograms) of the **same participant** before and after completing the fitness program.

---

## Hypotheses

**Null Hypothesis (H₀)**

The average weight before the program is equal to the average weight after the program.

**H₀: μ = 0**

where **μd** represents the mean of the paired differences.

**Alternative Hypothesis (H₁)**

The average weight before the program is different from the average weight after the program.

**H₁: μ ≠ 0**

---

# Step 1: Upload the Dataset

Upload **weight_before_after.csv**.

---

# Step 2: Open Tests for Mean

Navigate to:

**Statistical Analysis → Testing of Hypothesis → Tests for Mean**

---

# Step 3: Configure the Test

Select the following options.

| Field | Value |
|-------|-------|
| Select Sample Type | Paired Sample |
| Select Variable 1 | Before |
| Select Variable 2 | After |
| Hypothesized Mean (μ₀) | 0 |
| Alternative Hypothesis | Two Sided (≠) |


---

# Step 4: Run the Test

Click **Run Test**.

---

# Step 5: View Results

XInsight displays:

- Test Statistic
- Critical Value
- Conclusion

for different **Significance Levels (%)**.

<img width="1592" height="406" alt="image" src="https://github.com/user-attachments/assets/cd186519-c0ec-44df-915f-857b46b30051" />
---

# Tutorial 4: One-Sample Variance Test

## Objective

This tutorial demonstrates how to perform a **One-Sample Variance Test** in XInsight. This test is used to determine whether the variance of a population differs significantly from a specified value.

---

## Learning Scenario

A manufacturing company produces **steel bolts** with a target diameter of **10 mm**.

To ensure consistent quality, the company regularly checks whether the **variation in bolt diameters** meets the manufacturing specification.

A random sample of bolt diameters is collected to determine whether the population variance differs from the specified variance.

---

## Dataset

Use **bolt_diameter.csv**.

| Diameter (mm) |
|--------------:|
| 10.01 |
| 9.98 |
| 10.03 |
| 9.99 |
| 10.00 |
| 10.02 |
| 9.97 |
| 10.01 |
| 10.00 |
| 9.99 |

---

## Hypotheses

**Null Hypothesis (H₀)**

The population variance is equal to the specified variance.

**H₀: σ² = 0.0004**

**Alternative Hypothesis (H₁)**

The population variance is different from the specified variance.

**H₁: σ² ≠ 0.0004**

---

# Step 1: Upload the Dataset

Upload **bolt_diameter.csv**.

---

# Step 2: Open Tests for Variance

Navigate to:

**Statistical Analysis → Testing of Hypothesis → Tests for Variance**

---

# Step 3: Configure the Test

Select the following options.

| Field | Value |
|-------|-------|
| Select Sample Type | One Sample |
| Select Target Variable | Diameter |
| Hypothesized Variance (σ₀²) | 0.0004 |
| Alternative Hypothesis | Two Sided (≠) |

<img width="1920" height="932" alt="image" src="https://github.com/user-attachments/assets/a4233d76-15c2-4a9f-bfc7-6493fc2c71b3" />

---

# Step 4: Run the Test

Click **Run Variance Test**.

---

# Step 5: View Results

XInsight displays:

- Test Statistic
- Critical Value
- Conclusion

for different **Significance Levels (%)**.
<img width="1577" height="409" alt="image" src="https://github.com/user-attachments/assets/dd1f018e-1e9b-462b-8971-7f6f0558941d" />

---

# Tutorial 5: Two-Sample Variance Test

## Objective

This tutorial demonstrates how to perform a **Two-Sample Variance Test** in XInsight. This test is used to determine whether the variances of two independent populations differ significantly.

---

## Learning Scenario

A manufacturing company operates **two lathes (Lathe A and Lathe B)** to produce metal rods.

The quality control team wants to determine whether both machines produce rods with the **same level of consistency**. Since consistency is measured by the variability of rod diameters, a **Two-Sample Variance Test** is appropriate.

---

## Dataset

Use **lathe_variance.csv**.

| Lathe_A | Lathe_B |
|---------:|---------:|
| 25.01 | 24.95 |
| 24.99 | 25.08 |
| 25.00 | 24.92 |
| 25.02 | 25.10 |
| 24.98 | 24.89 |
| 25.01 | 25.12 |
| 25.00 | 24.90 |
| 24.99 | 25.09 |
| 25.02 | 24.91 |
| 25.00 | 25.11 |

Each column contains measurements collected from a different lathe.

---

## Hypotheses

**Null Hypothesis (H₀)**

The population variances of the two lathes are equal.

**H₀: σ₁² = σ₂²**

**Alternative Hypothesis (H₁)**

The population variances of the two lathes are different.

**H₁: σ₁² ≠ σ₂²**

---

# Step 1: Upload the Dataset

Upload **lathe_variance.csv**.

---

# Step 2: Open Tests for Variance

Navigate to:

**Statistical Analysis → Testing of Hypothesis → Tests for Variance**

---

# Step 3: Configure the Test

Select the following options.

| Field | Value |
|-------|-------|
| Select Sample Type | Two Sample |
| Select Variable 1 | Lathe_A |
| Select Variable 2 | Lathe_B |
| Alternative Hypothesis | Two Sided (≠) |
<img width="1920" height="852" alt="image" src="https://github.com/user-attachments/assets/41a1bbdd-786f-467e-859c-07800ddc9b88" />

---

# Step 4: Run the Test

Click **Run Variance Test**.

---

# Step 5: View Results

XInsight displays:

- Test Statistic
- Critical Value
- Conclusion

for different **Significance Levels (%)**.
<img width="1590" height="381" alt="image" src="https://github.com/user-attachments/assets/c7b494a0-7a66-43f7-a345-3def15782046" />

---
