# Using the Data Assistant Chatbot in IDEAS XInsight

## Overview

The **Data Assistant Chatbot** allows you to ask questions about your uploaded dataset using natural language. The chatbot automatically loads the dataset schema and metadata, then generates responses based on the structure and contents of the uploaded dataset.

> **Important:** Before using the chatbot, you must first upload and ingest a dataset.

---

## Step 1: Upload a Dataset

1. Open **IDEAS XInsight**.
2. Navigate to the **Ingestion** page from the left sidebar.
3. Upload your dataset (CSV, Excel, or supported format).
4. Complete the ingestion process.
5. Wait until the dataset appears in the application and is available for analysis.

**Note:** The chatbot cannot answer questions unless a dataset has been successfully ingested.

---

## Step 2: Open the Insights Page

1. Click **Insights** from the left navigation menu.
2. Select the dataset you want to analyze from the **Select a dataset** dropdown.

Once selected, XInsight displays:

- Dataset metadata
- Column-wise summary
- Suggested data types
- Numeric feature statistics
- Categorical feature information
- Correlation analysis

---

## Step 3: Configure the Local Language Model 

1. Open **Settings**.
2. Click **Browse File**.
3. Select a supported **GGUF model** file.
4. Enter a model display name.
5. You can select the checkbox of **Show SQL Query & Output expander in chat responses** based on your preference whether you want to see the generated SQL Query or not.
6. Click **Save Settings**.

The selected model will be used by the Data Assistant for generating responses.

---
<img width="1919" height="1023" alt="Screenshot 2026-06-19 112201" src="https://github.com/user-attachments/assets/1c7b8b12-554e-49e4-9aac-1dbdc96391cf" />
<img width="1919" height="1021" alt="Screenshot 2026-06-19 112343" src="https://github.com/user-attachments/assets/e7a9276f-669c-4c47-8907-262f48c4e681" />
<img width="1919" height="1018" alt="Screenshot 2026-06-19 112414" src="https://github.com/user-attachments/assets/87b47f29-5351-46d3-89f7-97355a870d94" />


## Step 4: Launch the Data Assistant

1. Click the **Ask Data** button located in the bottom-right corner of the screen.
2. The **Data Assistant** panel will open.

When the assistant starts, it automatically loads:

- Dataset schema
- Column names
- Data types
- Semantic types
- Dataset metadata
- Ask questions resgarding the uploaded schema
- Chatbot will give you answers about the dataset and display the generated SQL query based on your preference in the settings 

This schema becomes the context used by the chatbot to answer your questions.

---
<img width="1919" height="1032" alt="Screenshot 2026-06-19 112621" src="https://github.com/user-attachments/assets/b8ed433c-dfd2-4abd-b814-c5a5a45d5bc1" />
<img width="1919" height="1027" alt="Screenshot 2026-06-19 112648" src="https://github.com/user-attachments/assets/142e2764-be7d-4654-ac6c-d81846c3c5ac" />



## Key Point

The Data Assistant is **schema-aware**. It automatically loads the schema of the currently selected dataset and answers questions based on that uploaded dataset, making it easy to perform data exploration and analysis using natural language.
