# Factor Analysis Guide (Statistical Analysis Section)

Use this guide to perform and interpret **Factor Analysis** in the **Statistical Analysis** module.

---

## 1. Open Factor Analysis Section


1. Navigate to **Statistical Analysis** from the sidebar.
2. Upload or select your dataset.
3. Open the **Factor Analysis** section.
4. Gives the eigen values corresponding each feature

The application first displays the dataset preview along with variance information for each variable.

<!-- Screenshot 1: Initial Factor Analysis screen with dataset preview and variance table -->

<img width="1858" height="774" alt="Screenshot 2026-05-07 165546" src="https://github.com/user-attachments/assets/c5b060b7-12c1-418d-8344-199c2be69f13" />


---

## 2. Check Dataset Applicability

Before running factor analysis, the application validates whether the dataset is suitable using:

- **Bartlett’s Test**
- **KMO (Kaiser-Meyer-Olkin) Test**

Interpretation:

- A significant Bartlett’s test (typically p-value < 0.05) indicates that variables are correlated enough for factor analysis.
- Higher KMO values indicate better sampling adequacy.

If conditions are satisfied, the app displays:

- **“Applicable for factor analysis”**

<!-- Screenshot 2: Bartlett and KMO validation results -->
<img width="1821" height="770" alt="Screenshot 2026-05-07 163240" src="https://github.com/user-attachments/assets/9f72e8fa-c0e7-4d74-9f1c-5ec9f08409ba" />


---

## 3. Choose Number of Factors

After validation:

1. Select the desired number of factors from the dropdown.
2. The app computes:
   - Factor variance
   - Explained variance ratio
   - Cumulative variance

Tip:

- Lower number of factors -> simpler interpretation
- Higher number of factors -> more variance explained

<!-- Screenshot 3: Factor selection dropdown and variance output -->
<img width="1831" height="892" alt="Screenshot 2026-05-07 163327" src="https://github.com/user-attachments/assets/4e746a29-3e89-4918-95fa-6cc30285ff6e" />



---

## 4. Interpret Factor Loadings

The generated **Factor Loadings Table** shows the relationship between variables and latent factors.

Understanding the table:

- Higher absolute loading values indicate stronger relationships.
- Variables are grouped under the factor where they have the strongest loading.
- Positive and negative values indicate direction of association.

Example interpretation:

- `outgoing` and `sociable` strongly loading on the same factor may represent a **social behavior factor**.
- `dutiful` and `hard-working` loading together may represent a **discipline/productivity factor**.

<!-- Screenshot 4: Factor loadings and grouped feature output -->

<img width="1820" height="824" alt="Screenshot 2026-05-07 163833" src="https://github.com/user-attachments/assets/19dd6cc8-abbd-48d0-8f3c-17687b5e8441" />


---

## 5. Feature-to-Factor Mapping

The final section maps each feature to its dominant factor.

This helps in:

- Reducing dimensionality
- Identifying hidden patterns
- Grouping related variables
- Building interpretable latent constructs

Typical workflow:

1. Review factor loadings
2. Identify strongest factor for each feature
3. Interpret the meaning of each factor group

<!-- Screenshot 5: -->

<img width="1821" height="899" alt="Screenshot 2026-05-07 163852" src="https://github.com/user-attachments/assets/bc246569-0866-4827-ab85-3a0920e4820b" />

