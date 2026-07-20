# IDEAS-XINSIGHT Application

Welcome to the documentation for the XINSIGHT application built by Institute of Data Engineering, Analytics and Science Foundation-Technology Innovation Hub (IDEAS-TIH), @ Indian Statistical Institute, Kolkata.

This documentation explores how a user will potentially use XInsight and what functionalities this software has to offer.

## How to install

Please follow the steps below to install the XInsight application

1. Select for which user you want to install.
 <img width="452" height="317" alt="Screenshot 2026-07-20 160355" src="https://github.com/user-attachments/assets/d0fd965f-0daf-40f2-8d10-902551634507" />


2. Please go through the terms and conditions of the license agreement before accepting it.
 <img width="797" height="615" alt="Screenshot 2026-07-20 160718" src="https://github.com/user-attachments/assets/b30c2ba6-08c2-424f-b6ce-7a57e9458cec" />


3. Select the desired location where the software will be installed
 <img width="915" height="644" alt="Screenshot 2026-07-20 160808" src="https://github.com/user-attachments/assets/852c98f6-e48d-4cc2-840a-52ec0cfca366" />


4. You can keep the checklist selected to create a desktop shortcut (optional)
 <img width="790" height="607" alt="Screenshot 2026-07-20 160908" src="https://github.com/user-attachments/assets/632047ee-1860-40f7-9b90-2f6ca07f5d15" />


5. Select "Install" to begin installation.
  <img width="787" height="610" alt="Screenshot 2026-07-20 160941" src="https://github.com/user-attachments/assets/43cb4234-1263-41b2-bbee-e0dbbc4b075e" />


6. Please wait for a while while the software installs.
 <img width="792" height="607" alt="Screenshot 2026-07-20 161016" src="https://github.com/user-attachments/assets/2f1d8bae-3998-4577-b399-bf2da34a72fa" />


7. The installation is now completed. Select "Launch IDEAS-XINSIGHT" to get started with the software!
 <img width="791" height="603" alt="Screenshot 2026-07-20 161105" src="https://github.com/user-attachments/assets/013bae81-f03f-4ea9-9766-8f0b201c6581" />


8. Once you see this window, please wait for a couple of minutes (1-3 minutes depending on the device) for the app to open.
 <img width="1050" height="730" alt="Screenshot 2026-07-20 161200" src="https://github.com/user-attachments/assets/b20c1dc8-a437-4827-9d21-30e2a69f4ef3" />


## How to use

The software has 4 main functionalities-

1. Ingestion -> to upload data files in CSV and XSLX formats
2. Insights -> view details of the data uploaded
3. Storytelling -> charts and time series
4. Statistical Analysis -> various statistical measures and calculations
   This image shows the layout of the app.

<img width="1919" height="1032" alt="Image" src="https://github.com/user-attachments/assets/03108f9c-bd6a-476c-afa9-a5fc26a1f447" />

### Ingestion

If you are using this application for the first time, you must upload a dataset to begin exploring its features. The system cannot perform analysis unless at least one dataset exists in the database.

The maximum allowed file size is **2GB**.  
Supported file formats:

- CSV (.csv)
- Excel (.xlsx)

<img width="1919" height="1032" alt="Image" src="https://github.com/user-attachments/assets/a95c6392-34fa-42f3-9943-99c2978e3b81" />
#### Uploading a Dataset

1. Click **Browse** and select your file.
2. Click **Upload dataset**.

The application will:

- Load the dataset into the internal database
- Store it for further analysis and operations

If a dataset is no longer required, you can delete it from the database using the available delete option.

### Load Data from Database

You can also load data directly from external databases such as **SQLite**, **Microsoft SQL Server** and **PostgreSQL**.

After connecting successfully, you can select tables and load them into the application's internal database for further analysis.

<img width="1916" height="1029" alt="Image" src="https://github.com/user-attachments/assets/2ce0d2d8-7c18-42b6-8f62-86d93e15c050" />

## SQLite Connection

To connect to a SQLite database:

1. Select **SQLite** as the database type.
2. Provide the SQLite database file path.

The system will automatically:

- Establish the connection
- Detect all available tables in the database
- Display the tables for selection

You can then load selected tables into the internal database for further analysis.

## Microsoft SQL Server Connection

You can connect to Microsoft SQL Server in two ways:

### 1. Windows Authentication

- Select Windows Authentication
- Provide the server name (for example: `localhost`)
- Provide the port number if required

The system will connect using your Windows credentials.

### 2. SQL Server Authentication

Provide:

- Server name (for example: `localhost`)
- Port number
- Username
- Password
- Database name, if available

After successful connection, the application will:

- Display all available tables in the selected database
- Allow you to select tables
- Load selected tables into the internal database for further use

Once loaded, the data becomes available for analysis, insights generation, and storytelling modules.

### Insights

There are 8 functionalities within Insights. These include Data Info, Numerical Features, Categorical Features, Show Data, Bivariate Correlation, Multivariate Correlation, and Clustering. All the reports generated in each tab can be exported as PDF reports.
They can be found in the Insights section as a top bar.

<img width="1915" height="1028" alt="Image" src="https://github.com/user-attachments/assets/d5eb1f56-e353-4c88-89d5-6aef5c1f4b75" />

#### 1. Data Info

This tab shows 2 tables. The first table shows the total number of rows, columns, duplicate rows, and missing values. The second table contains a detailed column-wise summary. For each column, the user gets the following-

1. Summary statistics: Data type, number of unique values, missing values, zero values, outliers, and negative values.

2. Statistical Metrics (where applicable): Mean, median, skewness, kurtosis, 1st and 3rd quartiles, minimum, and maximum values.

3. Visualizations: A boxplot chart is included for each numerical column to visualize data distribution and outliers.

<img width="1918" height="1029" alt="Image" src="https://github.com/user-attachments/assets/75463332-7754-4501-aa9a-29f2541b6279" />

#### 2. Suggested Types

This tab shows 1 table. For each column, the user gets the following-

1. Coulmn name : The name of the columns.
2. Semantic Type : Semantic type suggests the user what the data mean i.e. the data type os the column.

#### 3. Numerical Features

This tab is to see statistics relevant to numerical columns only. Users can select the particular column from the dropdown provided. You get summary statistics such as the number of unique values, missing values, zeros, outliers, and negative values, and distribution metrics such as the mean, median, skewness, kurtosis, 1st and 3rd quartiles, minimum, and maximum. There is a histogram that shows the distribution of the selected column.

<img width="1919" height="1028" alt="Image" src="https://github.com/user-attachments/assets/32b8447e-f0e5-4eb3-90a0-ce3c900ecac0" />

#### 3. Categorical Features

This tab provides statistics relevant to categorical features only. Users can select the particular column from the dropdown provided. For each column, they get the number of unique values, missing values, empty rows, and rows containing only whitespaces. Formatting details like counts for rows containing only uppercase letters, alphabetic characters, or digits are also provided. For the selected column, you can see all the unique values present there. A bar chart is also present that shows the frequency of each category.

<img width="1919" height="1027" alt="Image" src="https://github.com/user-attachments/assets/c1019e28-ac55-4d2b-81a5-18d48b6176c0" />

#### 4. Show data

This module allows users to browse the raw dataset. To ensure smooth performance, 100 rows are loaded at a time. The user can use the dropdown menu to select a column and visualize its distribution, which is given by a quantile-quantile plot. The user also gets a p-value to determine if the data points follow a normal distribution.

#### 5. Bivariate Correlation

This tab performs automated bivariate analysis by dynamically selecting statistical tests and visualizations based on variable data types. Numeric–numeric relationships are analyzed using correlation coefficients and scatter plots. Categorical–numeric relationships are evaluated using non-parametric tests (Kruskal–Wallis) and boxplots. Categorical–categorical relationships are tested using Chi-square independence tests.

#### 6. Multivariate Correlation

This module features multivariate correlation analysis, providing heatmaps for numeric columns using Pearson, Kendall, and Spearman correlation methods. These heatmaps help identify relationships across the entire dataset at once.

#### 7. Clustering

This tab allows users to group similar records in the dataset using automated clustering. The tab offers three clustering options.

1. Basic Clustering groups data using all available numeric features and suggests an optimal number of clusters.
   Users can adjust the number of clusters and view how records are distributed across them.

2. PCA Clustering simplifies the data into two components to make cluster patterns easier to visualize. Clusters are displayed in a two-dimensional plot for clear visual separation.

3. Two-Feature Clustering allows users to select any two features and analyze how they form clusters together.
   This option is useful for focused, feature-level exploration.

For all options, the system evaluates cluster quality automatically.A silhouette score is shown to indicate how well the clusters are formed. Higher silhouette values represent better cluster separation.

### Storytelling

There are 3 functionalities within Storytelling and these include Measures and Dimensions, Charts, and Time Series. Similar to Insights, the results generated in this tab can be exported as PDF reports.
They appear as an overhead bar.

<img width="1919" height="1030" alt="Image" src="https://github.com/user-attachments/assets/fac74679-b348-4ac9-ae35-87ee06945fef" />

#### 1. Measures and Dimensions

This tab displays the data type of the columns, if they are numerical, indicated by MEASURE, or categorical, indicated by DIMENSION. Often, a column can be incorrectly classified as MEASURE just because they contain numeric values, when in reality they signify categorical values represented as numbers. Users can change the column type, and select "Save Measures and Dimensions" so that the new changes are saved.

#### 2. Chart Recommendations

The **Chart Recommendation Engine** automatically suggests the most suitable visualizations for a dataset.

It uses a **dual-engine approach**:

1.  **Lux Engine (Primary)** → Intelligent, ML-driven recommendations
2.  **Heuristic Engine (Fallback)** → Rule-based chart suggestions

This helps users quickly generate insights without manually choosing chart types.

#### 3. Charts

This tab lets users generate 6 types of charts. These include line chart, scatter plot, bar chart, pie chart, box plot, and histogram. User can fill up the required and optional values to generate the desired chart. Here is a demo of how to generate a line chart by selecting the desired columns for X axis, Y axis, and Colour. User has the option to either simply view the chart or to save it to the database. By saving a chart to the database, the user can recreate the previously generated chart without having to fill in the details each time.

#### 4. Time Series

This tab lets users perform time series analysis and forecasting of a particular column, provided an accurate "Date" or time column is provided. Users can choose confidence interval; and the forecasting period along with its unit (day/month/year). Users also has the option to ignore the last few periods, in case of any anomaly. Further, two types of predictions are possible- one is by choosing the default model and the other is by choosing a flexible model. The flexible model lets the user choose yearly, weekly, or daily seasonality and also to select the mode of seasonality, if it is additive or multiplicative. The model used for time series forecasting is Facebook Prophet, which has a property called "Changepoint prior scale". It is a hyperparameter that controls trend flexibility by determining how much the trend changes at potential changepoints. A higher value increases flexibility to fit frequent, drastic trend shifts (risk of overfitting), while a lower value creates a smoother, more rigid trend (risk of underfitting).

#### 5. Statistical Analysis

<img width="1681" height="746" alt="Screenshot 2026-05-07 182655" src="https://github.com/user-attachments/assets/f9f2b039-20bf-41ea-9434-820d474260b7" />


Statistical Analysis provides users analysis on testing of hypothesis and eda information as two-way table/multiway table and pivot table.
For more deatails on specific testing look into EXAMPLES folder.
