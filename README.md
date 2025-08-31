# Sales Forecasting Description

##  Overview
The **Sales Forecasting Description** project is part of the **Self-Paced Elevvo Machine Learning Internship Level 3**.  

This project focuses on analyzing and predicting sales trends using Walmart’s historical retail data. Sales forecasting is essential in retail for **inventory management, staffing, financial planning, and demand prediction**. By leveraging machine learning techniques, the project demonstrates how data-driven models can improve decision-making and optimize resources.  

The workflow includes **data preprocessing, feature engineering, exploratory data analysis (EDA), and implementation of advanced models** such as **XGBoost** and **LightGBM**, with performance comparisons across different feature selection strategies.

---

##  Table of Contents
- [Features](#features)  
- [Technologies Used](#technologies-used)   
- [Usage](#usage)  
- [Data Sources](#data-sources)  
- [Project Structure](#project-structure)  
- [Results & Visualizations](#results--visualizations)  

---

##  Features
- Data preprocessing and cleaning  
- Feature engineering and selection (**manual**, **k-best**, **recursive feature elimination (RFE)**, **full set**)  
- Exploratory data analysis (EDA) with Jupyter Notebook & interactive HTML export  
- Implementation and comparison of **XGBoost** and **LightGBM** models  
- Evaluation using **R²**, **RMSE**, and **R² drop** (to check generalization and overfitting)  
- Visualization of sales trends and model performance  

---

##  Technologies Used
- **Python**  
- **Jupyter Notebook**  
- **ydata-profiling**  
- **Pandas**, **NumPy**  
- **Scikit-learn**  
- **Matplotlib**, **Seaborn**  
- **XGBoost**, **LightGBM**  

---
##  Usage

1. Open Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

2. Run the notebooks in order:

   * `Data Analysis & Visualization.ipynb` → Perform EDA and visualize sales trends
   * `Data Preprocessing & Feature Engineering.ipynb` → Prepare and clean the dataset
   * `Feature Selection & Model Development.ipynb` → Apply feature selection, train models, and compare results

3. Alternatively, explore **`SalesForecastingDescriptionEDA.html`** for a static, interactive version of the EDA results.

---

##  Data Sources

Dataset: [Walmart Sales Forecasting Dataset (Kaggle)](https://www.kaggle.com/datasets/aslanahmedov/walmart-sales-forecast)

**Raw data files include:**

* `features.csv` → Economic & seasonal features (CPI, unemployment, fuel price, etc.)
* `stores.csv` → Store metadata
* `train.csv` → Training dataset with historical weekly sales
* `test.csv` → Test dataset for evaluation and prediction

---

##  Project Structure

```
Sales-Forecasting-Description/
│
├── Data/
│   ├── Raw Data/
│   │   ├── features.csv
│   │   ├── stores.csv
│   │   ├── train.csv
│   │   └── test.csv
│
├── Predictions/
│   ├── Weekly_Sales_Prediction.xlsx   # Model output predictions
│
├── Notebooks/
│   ├── Data Analysis & Visualization.ipynb
│   ├── Data Preprocessing & Feature Engineering.ipynb
│   ├── Feature Selection & Model Development.ipynb
│
├── SalesForecastingDescriptionEDA.html
└── README.md
```

---

##  Results & Visualizations

### LightGBM – Actual vs Predicted

<img width="1589" height="590" alt="LightGBM Predictions" src="https://github.com/user-attachments/assets/a14cf092-4870-4886-838b-df9315c62290" />

### XGBoost – Actual vs Predicted

<img width="1589" height="590" alt="XGBoost Predictions" src="https://github.com/user-attachments/assets/0dcc8876-fcb7-408e-81fd-124445014947" />

### Model Comparison – Validation R²

<img width="936" height="443" alt="Validation R²" src="https://github.com/user-attachments/assets/10d83297-b237-4a03-adcb-4d5d559e969c" />

### Model Comparison – Validation RMSE

<img width="932" height="541" alt="Validation RMSE" src="https://github.com/user-attachments/assets/c1ec7370-ecea-458f-946b-8b9bccaf9688" />

###  Model Comparison Summary

| Feature Set | XGB Val R² | LGBM Val R² | XGB Val RMSE | LGBM Val RMSE | XGB R² Drop | LGBM R² Drop |
| ----------- | ---------- | ----------- | ------------ | ------------- | ----------- | ------------ |
| Manual      | 0.9301     | **0.9597**  | 5804.13      | **4406.48**   | -0.0085     | 0.0077       |
| K-best      | 0.9217     | 0.9362      | 6139.64      | 5544.41       | -0.0262     | 0.0015       |
| RFE         | 0.9170     | 0.9567      | 6321.51      | 4568.02       | -0.0144     | 0.0065       |
| All         | 0.9309     | **0.9603**  | 5769.54      | **4371.43**   | -0.0107     | 0.0088       |

**Key Insights:**

* **LightGBM** consistently outperforms **XGBoost** across all feature sets.
* **Manual** and **All** feature sets yield the best results.
* Small R² drop values → Both models generalize well with only minor overfitting.

