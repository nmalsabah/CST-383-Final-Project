# Tech Layoffs Analysis (2020 - 2024)

## 📊 Project Overview

This project analyzes tech layoffs from 2020 to 2024 using a dataset from [Kaggle](https://www.kaggle.com/datasets/ulrikeherold/tech-layoffs-2020-2024). The goal is to understand how company characteristics influence company size after layoffs and predict post-layoff company size based on several factors.

As computer science students, we aimed to gain insights into job security in the tech sector, helping future graduates better understand which industries and companies might offer more stability.

---

## 🎯 Research Question

**How do various company characteristics affect company size after layoffs?**  

We focused on predicting `Company_Size_after_layoffs` using factors such as:
- Company size before layoffs
- Total funding raised
- Industry
- Maturity stage (e.g., startup, post-IPO)
- Percentage of workforce laid off
- Year of layoffs
- Country where layoffs occurred

---

## 🔍 Dataset Information

- **Source:** [Kaggle Dataset - Tech Layoffs 2020-2024](https://www.kaggle.com/datasets/ulrikeherold/tech-layoffs-2020-2024)
- **Features Used:**
  - `Company_Size_before_Layoffs`
  - `Money_Raised_in_$_mil`
  - `Industry`
  - `Stage`
  - `Percentage`
  - `Country`
  - `Year`
- **Target Variable:** `Company_Size_after_layoffs`

---

## ⚙️ Methods and Tools

- **Programming Language:** Python
- **Libraries Used:**
  - `pandas` and `NumPy` for data manipulation
  - `matplotlib` and `seaborn` for data visualization
  - `scikit-learn` for machine learning (Random Forest and Linear Regression)
- **Preprocessing Steps:**
  - Dropped irrelevant columns (`lat`, `lng`, `Date_layoffs`)
  - Handled missing values using median imputation and zero-filling for missing funding amounts
  - Encoded categorical variables using `LabelEncoder`

---

## 📈 Results and Visualizations

- The **Random Forest Regressor** significantly outperformed **Linear Regression**:
  - **Linear Regression R² Score:** 0.03 (Poor fit)
  - **Random Forest R² Score:** 0.79 (Good predictive capability)

- **Key Insights:**
  - The most influential factors were the percentage of layoffs and company size before layoffs.
  - Certain industries and maturity stages (such as startups) experienced higher workforce reductions.

- **Visualizations Included:**
  - Missing data heatmap before and after cleaning
  - Feature distributions before and after cleaning
  - Company size before vs. after layoffs by industry
  - Scatter plot relationship between Money Raised vs Laid Off
  - Scatter plot comparing actual vs. predicted layoffs using the Random Forest model

---

## 💡 Key Findings

- Companies that had larger sizes before layoffs and higher layoff percentages were more likely to experience significant reductions in size.
- Startups and specific industries, such as fintech and e-commerce, faced higher volatility.
- Random Forest proved to be the most effective model for predicting layoffs due to its ability to handle non-linear relationships and interactions between variables.

---

## 🔗 How to Run the Code

- **Run the Jupyter Notebook:**
   ```bash
   jupyter notebook CST383_Final_Project.ipynb
- **Note:**
   
   If there are kagglehub errors when initially running the notebook:
   - Run the following at the top of the imports: !pip install --upgrade --force-reinstall kagglehub
   - Run the notebook again
