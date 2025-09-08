# 📈 Dynamic Pricing Model for E-Commerce

## 🧠 Overview
This project is a dynamic pricing model that uses machine learning to optimize retail prices. It analyzes a dataset of retail transactions to predict future prices and quantities and evaluates the effectiveness of the models used.

---

## ❓ Problem Statement
The goal of this project is to predict the optimal `unit_price` of a product based on various influencing factors, such as quantity sold, shipping costs, and competitor pricing. The ultimate aim is to provide a data-driven approach to pricing to potentially increase revenue.

---

## 🔍 Approach & Methodology
- Analyzed a retail transaction dataset (`retail_price.csv`).
- Used features like `qty` (quantity), `total_price`, `freight_price`, and `lag_price` (previous month's price).
- Incorporated competitor data: `comp_1`, `comp_2`, `comp_3` (competitor prices) and `ps1`, `ps2`, `ps3` (competitor product scores).
- Employed two machine learning models: **Random Forest Regressor** and **XGBoost Regressor** to predict `unit_price`.
- Evaluated model performance using **Mean Absolute Error (MAE)** and **Mean Absolute Percentage Error (MAPE)** to measure prediction accuracy.

---

## 🧰 Tools & Technologies
- **Python**
- **Machine Learning Libraries**: Random Forest, XGBoost
- **Data Analysis**: Pandas, Numpy
- **Visualization**: Matplotlib, Seaborn

---

## 📈 Results
- The **XGBoost Regressor** model outperformed the **Random Forest** model with a lower MAE and MAPE.
- The project's output provides a data-driven method for setting dynamic prices.
- The model's predictions can be deployed to a real-time API to automate pricing recommendations.

---

## 💡 What I Learned
- Implemented and compared ensemble machine learning models for pricing optimization.
- Utilized time-series and competitor data to improve model accuracy.
- Evaluated model performance using key metrics like MAE and MAPE for business-relevant insights.

---

## 🚀 Next Steps
- Deploy the XGBoost model's predictions to a real-time API for automated pricing recommendations.
- Integrate the model into a live system for a continuous, data-driven pricing strategy.

---

### Detailed Project Background
> The project uses a dataset called `retail_price.csv` from Kaggle, which contains various features related to retail sales. The goal is to predict the optimal `unit_price` based on other factors. This model is designed to help businesses move away from static pricing and adopt a flexible strategy that adapts to market changes and competitive pressures. The use of XGBoost, a model known for its high performance, ensures that the predictions are both accurate and reliable. The model's ability to factor in competitor pricing and product ratings makes it a robust tool for maintaining a competitive edge in the market. The final outcome is a practical, data-driven solution that aims to provide businesses with a competitive advantage and a clear path to increasing revenue.
