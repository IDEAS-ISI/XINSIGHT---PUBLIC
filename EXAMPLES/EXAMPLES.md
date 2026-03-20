This documentation will follow the various ways you can use the XInsight application.

## Scenario

Analyzing a retail sales dataset

## Step 1: Data Ingestion

1. Launch IDEAS XInsight
2. Click **Ingestion** tab

<img width="1919" height="953" alt="Image" src="https://github.com/user-attachments/assets/7969ece4-a426-486f-aa28-44769609fe87" />

3. Upload `SampleSuperstore.csv`
4. File is stored in database

## Step 2: Explore Data Info

1. Click **Insights** tab
2. Select "Data Info" from the overhead bar
3. **Select a Dataset:** Choose a dataset from the dropdown menu
   <img width="1919" height="936" alt="Image" src="https://github.com/user-attachments/assets/d25ee2a7-3cf0-4fe8-9fd2-ad7543601943" />
4. Meta Data

 <img width="600" alt="Insights data info" src="https://github.com/user-attachments/assets/befe2d7e-673b-40d7-bbed-d8ba0f5c53ee" />

5. Column Wise Summary: shows data types and patterns for each columns

 <img width="600:" alt="Insights data info" src="https://github.com/user-attachments/assets/0e597be8-9f8e-4383-8b8b-3478cb08d137" />

## Step 3: Numeric Analysis

1. Inside **Insights** tab, select "Numeric Features" from the overhead bar.
2. Select the desired column from the dropdown menu labeled **What column do you want to choose?**
3. Select **Sales**

<img width="1916" height="935" alt="Image" src="https://github.com/user-attachments/assets/58dd6d28-a6d5-4830-9037-971edf9c2665" />
4. **Visualization:** Histogram showing sales distribution

   <img width="600" alt="Ingestion numeric 2" src="https://github.com/user-attachments/assets/795df4d8-0742-4a4f-8c48-ded582d28b9a" />

## Step 4: Categorical Exploration

1. Select column from the dropdown **Choose a categorical feature**
2. Select **Sub-Category**

<img width="1916" height="907" alt="Image" src="https://github.com/user-attachments/assets/edc9b4f5-41e5-4746-9352-fdaed0fbff37" />

3. **Visualization:** Bar plot showing category distribution

 <img width="600" alt="screencapture-localhost-8501-2026-02-06-16_43_40" src="https://github.com/user-attachments/assets/5efa8552-a92f-4ac2-852c-a505341a1128" />

## Step 5: See data

1. Select **"Show Data"**
2. 100 rows are loaded at a time
   <img width="1919" height="932" alt="Image" src="https://github.com/user-attachments/assets/eded8ba9-7fee-4bae-a62a-95f9b7e440b1" />
3. Select a column from the dropdown menu **Select a column to check its Distribution** 5. Select **Quantity** 6. You get the p-value and a quantile-quantile plot for the column.

 <img width="600" alt="show data 2" src="https://github.com/user-attachments/assets/7e618dfb-837a-4d43-8480-7fbfbcbcb237" />

4. **Conclusion:** The data points are not normally distributed.

## Step 6: Correlation between 2 columns

1. Select **Bivariate-Correlation**
2. Select any 2 columns
3. Select **Profit** and **Discount** - both numerical columns
4. For numerical columns, the following results are obtained: Pearson's correlation coefficient, Kendall's correlation, Spearman's correlation, and a
   scatter plot visualization
5. This is how it shows up

<img width="1919" height="929" alt="Image" src="https://github.com/user-attachments/assets/eb0e62eb-6ae6-4d69-b44c-e6db1e0d8f0c" />
 6. Now, select **Sales** and **Sub-Category** - sales being a numeric column and sub-category being a categorical column 7. For a mix of numeric and categorical columns, Kruskal-Wallis test is performed and a box plot is visualized 8. This is the result

<img width="1919" height="947" alt="Image" src="https://github.com/user-attachments/assets/f311b6e6-fd57-44cd-8260-820f150cfa7e" />
 9. Now, select **Ship Mode** and **Sub-Category** - both categorical variables. 10. When both columns are categorical, we get a chi-square test, contingency table, and heatmap visualization. 11. This is the result.

<img width="1919" height="929" alt="Image" src="https://github.com/user-attachments/assets/d157d286-bf31-410c-b1fd-5a3f55f3a7c2" />

## Step 7: Multivariate Correlation

1. Select **Multivariate-Correlation**
2. You get the correlation between all the numeric features.

<img width="600" alt="multivariate" src="https://github.com/user-attachments/assets/a5a49752-414c-49e5-a89d-fe5f32752e38" />
