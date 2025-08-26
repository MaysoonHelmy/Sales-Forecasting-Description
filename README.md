# Sales Forecasting Description

## Overview

The **Sales Forecasting Description** project is part of the **Self-Paced Elevvo Machine Learning Internship Level 3**.  

It is designed to analyze and predict sales trends using historical data from Walmart. Sales forecasting is crucial in retail for **inventory management, staffing, financial planning, and demand prediction**. By leveraging machine learning techniques, this project demonstrates how data-driven models can improve decision-making and optimize resources.  

The project includes data preprocessing, feature engineering, exploratory data analysis (EDA), and implementation of advanced models (**XGBoost** and **LightGBM**) with performance comparisons across different feature selection strategies.  

## Table of Contents

- [Features](#features)  
- [Technologies Used](#technologies-used)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Data Sources](#data-sources)  
- [Project Structure](#project-structure)  
- [Results & Visualizations](#results--visualizations)  
- [Contributing](#contributing)  
- [License](#license)  

## Features

- Data preprocessing and cleaning  
- Feature engineering and selection (manual, k-best, recursive feature elimination, full set)  
- Exploratory data analysis (EDA) with notebook and interactive HTML export  
- Implementation and comparison of **XGBoost** and **LightGBM** models  
- Evaluation using **R²**, **RMSE**, and R² drop (overfitting/generalization check)  
- Visualization of sales trends and model performance  

## Technologies Used

- Python  
- Jupyter Notebook  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  
- Seaborn  
- XGBoost  
- LightGBM  

## Installation

To set up the project locally:  

```bash
# Clone the repository
git clone https://github.com/MaysoonHelmy/Sales-Forecasting-Description.git  

# Navigate to the project directory
cd Sales-Forecasting-Description
````

## Usage

1. Open Jupyter Notebook:

   ```bash
   jupyter notebook
   ```
2. Run the notebooks in the following order:

   * `Data Analysis & Visualization.ipynb` – Perform EDA and visualize sales trends.
   * `Data Preprocessing & Feature Engineering.ipynb` – Prepare and clean the dataset.
   * `Feature Selection & Model Development.ipynb` – Apply feature selection, train models, and compare results.
3. Alternatively, review **`SalesForecastingDescriptionEDA.html`** for a static, interactive version of the EDA results.

## Data Sources

The dataset used in this project is sourced from Kaggle:
📂 [Walmart Sales Forecasting Dataset](https://www.kaggle.com/datasets/aslanahmedov/walmart-sales-forecast)

Raw data files include:

* `features.csv` – Additional data such as CPI, unemployment, fuel price, etc.
* `stores.csv` – Metadata about stores.
* `train.csv` – Training dataset containing historical weekly sales.
* `test.csv` – Test dataset for model evaluation and prediction.

## Project Structure

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

## Results & Visualizations

### Model Comparison – Validation R²

<img width="936" height="443" alt="image" src="https://github.com/user-attachments/assets/10d83297-b237-4a03-adcb-4d5d559e969c" />

### Model Comparison – Validation RMSE

<img width="932" height="541" alt="image" src="https://github.com/user-attachments/assets/c1ec7370-ecea-458f-946b-8b9bccaf9688" />

### Model Comparison - Overfitting

<img width="921" height="549" alt="image" src="https://github.com/user-attachments/assets/cdc6f2b1-a9bc-434d-ad24-749d4877731c" />

### 🏆 Model Comparison Summary (Validation Performance)

| Feature Set | XGB Val R² | LGBM Val R² | XGB Val RMSE | LGBM Val RMSE | XGB R² Drop | LGBM R² Drop |
| ----------- | ---------- | ----------- | ------------ | ------------- | ----------- | ------------ |
| manual      | 0.9226     | **0.9660**  | 6351.29      | **4211.57**   | 0.0017      | 0.0052       |
| kbest       | 0.8940     | **0.9236**  | 7435.66      | **6310.00**   | 0.0099      | 0.0179       |
| rfe         | 0.9118     | **0.9600**  | 6783.19      | **4568.35**   | 0.0004      | 0.0064       |
| all         | 0.9243     | **0.9671**  | 6282.98      | **4141.62**   | 0.0031      | 0.0056       |

**Key Insights:**

* **LightGBM** consistently outperforms **XGBoost** across all feature sets.
* The **manual** and **all** feature sets yield the best results overall.
* R² drop values are small, indicating both models generalize well with only minor overfitting.

## Contributing

This project is a personal learning project 

## License

This project is not licensed. It is intended for educational and practice purposes only.
