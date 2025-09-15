# 📈 Pricing and Deals Optimization Model for E-Commerce

## 🧠 Overview
This project is a comprehensive dynamic pricing model that uses a multi-model machine learning approach to optimize retail prices. It analyzes a dataset of retail transactions to not only predict sales but also provide a prescriptive solution for setting optimal prices and profit margins.

---

## ❓ Problem Statement
The goal of this project is to move away from static pricing by predicting a product's optimal price based on various influencing factors, including shipping costs, quality scores, and, most critically, competitor pricing. The ultimate aim is to provide a data-driven approach to pricing that maximizes revenue and profitability in a competitive market.

---

## 🔍 Approach & Methodology
The project employed a hybrid, multi-model approach to solve the problem and move from pure prediction to a prescriptive solution.

1.  **Exploratory Data Analysis and Feature Engineering**: The project began with an extensive analysis of a retail transaction dataset. Key features were engineered to capture the full market picture, including:
    * **Competitive Intelligence**: `price_ratio` and `price_diff` to quantify our product's price against top competitors.
    * **Profitability Metrics**: `revenue`, `profit`, and `margin` for both our products and competitors.
    * **Temporal and Behavioral Features**: `weekday`, `holiday`, and `price_change` to account for fluctuations in consumer behavior.

2.  **Predictive Modeling**: Multiple models were evaluated to find the most accurate predictor of quantity sold (`qty`):
    * **ARIMA**: A time-series model that showed a poor fit with a high **MAE of 29.68** and **RMSE of 38.76**, indicating that demand was not primarily driven by simple time trends.
    * **XGBoost**: A powerful tree-based model that performed exceptionally well, achieving a much lower **MAE of 9.44** and **RMSE of 12.09**. This model's success confirmed that the relationships between price, competitors, and demand were complex and non-linear.

3.  **Price Elasticity Analysis**: To derive actionable business insights, an **OLS (Ordinary Least Squares) regression model** was used to calculate the price elasticity of demand for each product category.
    * The analysis showed that categories like `computers_accessories` had a high elasticity of **-3.11**, indicating that demand is highly sensitive to price changes.
    * Conversely, categories like `perfurmery` had a low elasticity of **-1.01**, suggesting that demand for these products is less sensitive to price.

4.  **Prescriptive Modeling (Hybrid Neural Network)**: The final step was building a **hybrid neural network** using TensorFlow and Keras. This model was a sequence of three interconnected models designed to provide a prescriptive output:
    * Model 1 predicted the optimal `freight_price`.
    * Model 2 predicted the optimal `unit_price`.
    * Model 3 predicted the final `optimized_total_price`, combining the outputs of the previous two models to provide a complete, actionable pricing recommendation.

---

## 🧰 Tools & Technologies
-   **Python**: The primary language for data analysis and modeling.
-   **Data Analysis**: Pandas, NumPy
-   **Machine Learning**: Scikit-learn, XGBoost, Statsmodels, TensorFlow, Keras
-   **Visualization**: Matplotlib, Seaborn
-   **Model Explainability**: SHAP (SHapley Additive exPlanations)

---

## 📈 Results
-   **High Predictive Accuracy**: The XGBoost model demonstrated high predictive power with a low **MAE of 9.44** and **RMSE of 12.09**, proving its ability to accurately forecast sales.
-   **Actionable Insights**: The price elasticity analysis provided a clear framework for category-specific pricing strategies. The **SHAP analysis** further revealed that **competitor prices were the most influential factor** in predicting sales, validating the core hypothesis.
-   **Prescriptive Solution**: The final hybrid neural network provides a direct, actionable output by generating an optimized price recommendation for any given product, enabling a proactive and data-driven approach to revenue management.

---

## 💡 What I Learned
-   **The Power of a Multi-Model Approach**: I learned that a single model isn't always the solution. By using a time-series model, a powerful tree-based model, and a neural network, I gained a comprehensive understanding of the data and built a robust, prescriptive solution.
-   **Translating Metrics to Business Value**: I learned to move beyond technical metrics like MAE and RMSE by translating them into tangible business insights, such as understanding which product categories are most sensitive to price changes.
-   **Model Explainability**: The use of SHAP was crucial in understanding the "why" behind the predictions, allowing me to confidently explain to stakeholders which factors were most important in the pricing model.

---

## 🚀 Next Steps
-   Integrate the hybrid neural network model into a live system to provide automated pricing recommendations.
-   Conduct A/B testing on a subset of products to measure the real-world revenue and profit uplift generated by the model.
-   Refine the model by incorporating external data sources such as real-time competitor prices or market-wide demand signals.
