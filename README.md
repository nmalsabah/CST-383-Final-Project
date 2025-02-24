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

- **Model Comparison:**
  - **Linear Regression:** Initial attempt at predicting layoffs.
    - **R² Score:** 0.03 (Poor fit, indicating the model struggled with non-linear relationships)
    - Feature importance was analyzed using model coefficients, showing both positive and negative impacts of features on layoffs.
  - **Random Forest Regressor:** Used after observing poor performance with Linear Regression.
    - **R² Score:** 0.79 (Indicates strong predictive power and better handling of non-linear patterns)
    - Feature importance revealed significant factors like percentage of layoffs and company size before layoffs.

- **Visualizations Included:**
  - Missing data heatmap before and after cleaning
  - Feature distributions before and after cleaning
  - Company size before vs. after layoffs by industry
  - Scatter plot showing the relationship between Money Raised and Laid Off
  - Bar chart of total layoffs by company
  - Bar chart of the total layoff percentages by company
  - Scatter plot comparing actual vs. predicted layoffs using Linear Regression (showing poor performance)
  - Scatter plot comparing actual vs. predicted layoffs using the Random Forest model

---

## 💡 Key Findings

- Companies with larger sizes before layoffs and higher layoff percentages were more likely to experience significant reductions in size.
- Startups and specific industries (such as retail and consumer) faced higher volatility.
- Random Forest was the most effective model for predicting layoffs, as it captured non-linear relationships and complex interactions between variables better than Linear Regression.
- The feature importance analysis showed:
- For **Linear Regression**, the most significant features were the company's **Stage** and the **Year** of layoffs:
  - A negative coefficient for **Stage** (-13.02) shows that more mature companies (e.g., post-IPO) tend to have fewer layoffs.
  - A positive coefficient for **Year** (9.41) indicates that layoffs increased in more recent years, reflecting industry trends.
  - The **Percentage** also showed a positive impact, meaning higher percentages of workforce reductions were linked to increased layoffs.
- For **Random Forest**, the most influential factors were **Company Size before Layoffs** and the **Percentage**:
  - **Company_Size_before_Layoffs** had the highest importance score (0.78), indicating that larger companies were more likely to experience higher numbers of layoffs. This suggests that company size is a strong predictor of the overall impact of layoffs.
  - **Percentage** of layoffs (0.13) was also a significant factor, meaning that companies laying off a higher percentage of their workforce were more likely to experience larger total layoffs.
  - Other features, such as **Money_Raised_in_$_mil** and **Stage**, had relatively low importance scores, suggesting that these factors had a smaller influence on predicting the total number of layoffs in this model.

---

## 🔗 How to Run the Code

- **Run the Jupyter Notebook:**
   ```bash
   jupyter notebook CST383_Final_Project.ipynb
- **Note:**
   
   If there are kagglehub errors when initially running the notebook:
   - Run the following at the top of the imports: !pip install --upgrade --force-reinstall kagglehub
   - Run the notebook again

---

## 👥 Team Members
- **Deborah Shaw**
- **Nicole Al-Sabah**
- **Chika Starks**

---

## 📚 References
- [Kaggle Dataset: Tech Layoffs 2020-2024](https://www.kaggle.com/datasets/ulrikeherold/tech-layoffs-2020-2024)
- [Random Forest Algorithm Explanation - GeeksforGeeks](https://www.geeksforgeeks.org/random-forest-algorithm-in-machine-learning/)
- [scikit-learn Documentation](https://scikit-learn.org/)
- [Seaborn Heatmap for Missing Values Article](https://medium.com/@HildaPosada/finding-and-visualizing-missing-data-in-python-using-missingno-and-seaborn-d4cf0452b9e9)
- [Matplotlib Colormap Documentation](https://matplotlib.org/stable/users/explain/colors/colormaps.html)
  
