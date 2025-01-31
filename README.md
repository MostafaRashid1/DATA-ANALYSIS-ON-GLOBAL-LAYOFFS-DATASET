# 🗄️ SQL Data Cleaning - World Layoffs Dataset
### 📌 Project Overview
This project focuses on **data cleaning** using SQL on the **World Layoffs dataset**. The dataset contains information on layoffs across industries, including company details, locations, and funding.  
We clean the dataset by **removing duplicates, handling missing values, standardizing data, and formatting dates** for further analysis.

### 🔍 Dataset Details
- **Source:** [Kaggle: Layoffs Dataset](https://www.kaggle.com/datasets/swaptr/layoffs-2022)
- **Size:** Multiple columns including company name, location, industry, layoffs count, and funding.
- **Cleaning Tasks:** 
  - Duplicate removal
  - Standardizing company & industry names
  - Handling missing values
  - Formatting **date columns**
  - Removing unnecessary rows and columns

### 🛠 Tools Used
- **Database:** MySQL / PostgreSQL  
- **SQL Queries:** `SELECT`, `UPDATE`, `DELETE`, `ALTER TABLE`, `JOIN`, `CTE`, `WINDOW FUNCTIONS`  

---

## 📊 **Key Data Cleaning Steps**
### 1️⃣ **Removing Duplicates**
✔ Used **`ROW_NUMBER()` with `PARTITION BY`** to find duplicate rows.  
✔ Deleted duplicate rows while keeping only unique entries.

### 2️⃣ **Standardizing Data**
✔ Fixed **industry names** (e.g., merged `"Crypto Currency"` and `"CryptoCurrency"` → `"Crypto"`).  
✔ Trimmed trailing periods from **country names** (e.g., `"United States."` → `"United States"`).  
✔ Updated missing **industry names** using company-wise comparisons.

### 3️⃣ **Handling Null Values**
✔ Converted empty strings to **NULL** for easier handling.  
✔ Retained some NULL values in `total_laid_off`, `percentage_laid_off`, and `funds_raised_millions` to preserve **data integrity**.  

### 4️⃣ **Date Formatting**
✔ Converted `date` column from **text format** to **DATE format** using `STR_TO_DATE()`.  

### 5️⃣ **Deleting Unnecessary Data**
✔ Removed rows where both `total_laid_off` and `percentage_laid_off` were NULL.  
✔ Dropped the `row_num` column after cleaning.  
