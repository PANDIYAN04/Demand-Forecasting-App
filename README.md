# Demand Forecasting Using Machine Learning

An end-to-end Machine Learning project that predicts product demand using historical retail data, an XGBoost regression model, and an interactive Streamlit web application.

## Project Overview

Demand forecasting helps businesses estimate future product demand and make better decisions about inventory management, pricing, promotions, and stock planning.

This project uses historical retail data to train an **XGBoost Regressor** that estimates product demand based on product price, discount, inventory level, promotion status, competitor pricing, and product category.

The trained model is integrated into a **Streamlit web application**, allowing users to enter product details and receive an estimated demand in units.

## Key Features

- Interactive demand prediction through a Streamlit interface.
- XGBoost regression for demand estimation.
- Exploratory Data Analysis (EDA) and data visualization.
- Categorical feature encoding using LabelEncoder.
- Hyperparameter optimization using RandomizedSearchCV.
- Cross-validation for model selection.
- Model evaluation using Root Mean Squared Error (RMSE).
- Feature importance analysis.
- Saved model and encoder artifacts for application use.

## Technologies Used

- **Programming Language:** Python
- **Machine Learning:** XGBoost, Scikit-learn
- **Data Analysis:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Web Application:** Streamlit
- **Model Persistence:** Pickle
- **Development Environment:** Jupyter Notebook / VS Code

## Dataset

The dataset contains **76,000 rows and 16 columns** in the current project copy, covering retail-related information such as product and store identifiers, dates, categories, inventory, sales, pricing, promotions, weather, seasonality, and demand.

The model uses six input features:

| Feature | Description |
|---|---|
| Price | Product selling price |
| Discount | Discount value |
| Inventory Level | Available inventory |
| Promotion | Promotion indicator (0 or 1) |
| Competitor Pricing | Competitor's product price |
| Category | Product category |

**Target Variable:** `Demand`

The current dataset includes five product categories: Clothing, Electronics, Furniture, Groceries, and Toys.

## Machine Learning Workflow

1. **Data Loading:** Load the retail dataset using Pandas.
2. **Exploratory Data Analysis:** Explore data distributions, relationships, and patterns.
3. **Feature Selection:** Select six input features and the demand target.
4. **Categorical Encoding:** Convert product categories into numerical values using LabelEncoder.
5. **Train-Test Split:** Split the data into training and testing sets using an 80:20 ratio.
6. **Model Training:** Train an XGBoost Regressor for demand prediction.
7. **Hyperparameter Tuning:** Use RandomizedSearchCV with 3-fold cross-validation to search for suitable model parameters.
8. **Model Evaluation:** Evaluate predictions on the test set using RMSE.
9. **Model Saving:** Save the trained model and category encoder using Pickle.
10. **Deployment:** Integrate the saved artifacts into a Streamlit application for interactive predictions.

## Project Structure

```text
Demand-Forecasting/
│
├── app.py
├── analysis.ipynb
├── machine_learning.ipynb
├── demand_forecasting.csv
├── preprocessed_demand_forecasting_data.csv
├── xgboost_demand_model.pkl
├── label_encoders.pkl
└── README.md
```

## Installation

**1. Clone the repository**

```bash
git clone <your-repository-url>
cd Demand-Forecasting
```

Replace `<your-repository-url>` with your actual GitHub repository URL.

**2. Install the required libraries**

```bash
python -m pip install streamlit pandas numpy scikit-learn xgboost matplotlib seaborn jupyter
```

**3. Run the Streamlit application**

```bash
streamlit run app.py
```

**4. Make a prediction**

- Open the local URL displayed in your terminal.
- Enter the product price, discount, inventory level, promotion status, and competitor price.
- Select a product category.
- Click **Predict Demand**.
- View the model's estimated demand in units.

## Retraining the Model

Open `machine_learning.ipynb` in Jupyter Notebook or VS Code and execute the cells in order. The notebook handles feature preparation, category encoding, model training, hyperparameter tuning, evaluation, and artifact saving.

If the model or category mapping changes, regenerate the saved artifacts and ensure the application uses the matching files.

## Applications

- Retail demand estimation.
- Inventory and stock planning support.
- Pricing and promotional decision support.
- Understanding factors associated with product demand.
- Exploring machine learning regression and model deployment.

## Limitations

- Predictions are estimates based on patterns learned from historical data, not guaranteed sales outcomes.
- The model uses only six features and does not directly consider other available variables such as date, weather, region, or seasonality.
- The train-test split does not use a fixed random seed, so evaluation results may vary between runs.
- The application displays predicted demand as an integer.
- The current implementation does not use a time-based validation strategy, so its evaluation does not establish how well it forecasts demand for future dates.
- Pickle artifacts should only be loaded from trusted sources.

## Learning Outcomes

Through this project, I explored the end-to-end machine learning workflow, including data analysis, feature selection, categorical encoding, regression, hyperparameter tuning, cross-validation, model evaluation, artifact persistence, and building an interactive prediction application.


**Pandiyan M**

Machine Learning | Python | Data Analysis | Predictive Modeling

---

*This project was developed for learning and demonstration purposes. Predictions should be validated against real-world business requirements before operational use.*
