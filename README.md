# Corporacíon Favorita Store Sales Forecasting

This project uses machine learning to predict daily grocery store sales using the publicly available dataset from the Kaggle competition [Store Sales - Time Series Forecasting](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/data) for an Ecuadorian retailer. It aims to help the business optimize inventory and reduce waste by forecasting demand for product families in each store.

## Overview (Business Understanding)

The purpose of this project is to develop a robust time series forecasting system that accurately predicts daily unit sales for the Ecuadorian grocery retail chain, Corporación Favorita. The forecasting system will operate at the level of individual stores and product families (broad product categories), using historical sales and external data. Accurate forecasting is essential in the grocery sector: overstocking leads to perishable inventory waste and increased storage costs, while understocking results in lost sales, customer dissatisfaction, and missed business opportunities.

By leveraging machine learning, this project intends to outperform manual or heuristic-based forecasting methods that are typically used in practice. The final deliverables will include a trained and validated ML model, insightful data visualizations, and an interactive web application that allows non-technical users to explore forecasts and patterns intuitively through a Streamlit-powered dashboard.

---

### Stakeholders

This project is designed to serve a variety of stakeholders across the retail organization:

* **Store Managers and Inventory Planners** rely on accurate forecasts to manage inventory effectively, reducing waste and avoiding out-of-stock situations.

* **Sales and Marketing Teams** can use forecasted sales to align promotional activities and adjust campaign timing and budgets accordingly.

* **Executive Management** needs aggregate sales forecasts to make budgeting, supply chain, and resource allocation decisions.

* **End Customers**, while not direct users of the system, benefit from improved product availability and service levels.

---

### Business Requirements

The system must be able to forecast daily unit sales for every combination of store and product family for a defined forecast window. For this project, the forecast period is 16 days, corresponding to the test dataset provided. However, the model should be flexible enough to extend this forecasting horizon as needed in the future.

The evaluation of the model’s performance will use the Root Mean Squared Logarithmic Error (RMSLE), the official metric of the Kaggle competition this dataset comes from. One objective is to beat naive benchmarks, such as using the sales from the same day one year ago.

To achieve this, the model will be enhanced through thoughtful feature engineering. It will incorporate relevant variables such as promotional status (`onpromotion`), oil prices, holidays and local events, temporal indicators (day of the week, month), and engineered features like lagged sales and rolling averages. These features aim to provide the model with sufficient context to learn patterns in seasonality, external influences, and trend shifts.

Beyond forecasting, usability is key. The project will include an interactive Streamlit dashboard where users can:

* Select a store and product family to view forecasts.

* Explore recent historical sales alongside predicted values.

* Visualize trends, seasonality, and confidence intervals.

Finally, transparency and reproducibility are vital to this project. Every notebook will clearly state its purpose, inputs, outputs, and reasoning in markdown documentation. All code will be maintained using Git and hosted on GitHub to provide a version-controlled, reviewable development history.

---

### Expected Outcomes

At the conclusion of the project, expect to have:

1. A machine learning model capable of making daily sales predictions for each store and product family.

2. Data-driven insights such as identification of top-performing product categories, seasonality patterns, and the impact of external factors like oil prices or national holidays.

3. An interactive Streamlit web application deployed on Render that enables real-time exploration of the forecasts and model insights.

4. A fully documented, modular, and reproducible codebase that meets academic and professional standards, including Jupyter Notebooks with step-by-step analysis and explanatory markdown cells.

This system will serve as a proof-of-concept for implementing data-driven forecasting tools in retail environments, with the potential for real-world adoption and future scaling.

## Dataset

To provide immediate context, the dataset used in this project originates from Corporación Favorita, a prominent grocery retailer in Ecuador, and was made available through a Kaggle competition. It offers detailed and diverse historical data from several sources. The `train.csv` file contains records of historical sales. Each row represents the number of units sold for a specific store and product family on a given date. The primary fields include `date`, `store_nbr`, `family`, `sales`, and `onpromotion`, which indicates the number of items from that family on promotion on that date.

The `test.csv` file mirrors the structure of the training data but applies to a future period, specifically from August 16 to August 31, 2017. Notably, it excludes the `sales` column as it is the target variable to be predicted. The `stores.csv` file provides metadata about each store, such as its city, state, type (A to D), and a clustering category that groups similar stores together.

The `holidays_events.csv` file records significant events and holidays that may influence customer behavior. Important columns include `type`, `locale`, `description`, and a `transferred` flag, which denotes whether a holiday was officially moved to another date. Accurately handling this column is vital for time-series forecasting, as it impacts consumer patterns.

The `oil.csv` file offers daily oil price data. Since Ecuador's economy is closely tied to oil, fluctuations in these prices are considered potentially influential on customer purchasing behavior. Finally, `transactions.csv` captures the number of daily transactions per store, functioning as a proxy for customer traffic and offering additional context to sales trends.

The training set spans more than four years of daily sales data, covering 54 stores and 33 product families, and contains roughly three million records. This dataset is freely accessible for academic use and can be downloaded from the competition's Kaggle page after registering for a free account. Registration with a free Kaggle account is required to download the data files.

## Methodology

This project adheres to the CRISP-DM (Cross Industry Standard Process for Data Mining) methodology. This structured framework ensures a systematic approach to solving predictive problems through data analysis. The process begins with Business Understanding, which defines the core objective: to forecast daily unit sales per store and product family. This objective aligns with broader business goals such as optimizing inventory levels, enhancing promotional strategies, and increasing revenue.

In the Data Understanding phase, exploratory analysis is conducted on all datasets to detect missing values, outliers, seasonality, trends, and correlations. Visual and statistical summaries help in identifying structural shifts and potential anomalies, such as sales disruptions during national holidays or natural disasters.

Data Preparation involves merging relevant datasets, addressing missing or inconsistent values, and encoding categorical variables. Time-based features like the day of the week, month, and holiday indicators are engineered. Lag features and rolling averages are also introduced to capture historical dependencies and smooth trends. Throughout this process, precautions are taken to avoid data leakage, ensuring a clean training environment.

During Modeling, a selected subset of algorithms is implemented based on time constraints and suitability for the data. A time series model such as Prophet is initially tested to account for seasonality and trend components. In parallel, a feature-based machine learning model such as XGBoost is considered for its ability to handle categorical variables and engineered features like lagged sales or promotions. Rather than evaluating a wide range of models, the focus is placed on developing and refining one to two well-performing approaches, balancing accuracy with interpretability. Hyperparameter tuning is performed where feasible using randomized or grid search.

The Evaluation phase focuses on assessing model accuracy using RMSLE (Root Mean Squared Logarithmic Error), which aligns with the competition's metric. Supplementary evaluation methods include plotting actual versus predicted values, analyzing residuals, and calculating secondary metrics like R² and RMSE. Baseline models, such as naive historical averages, are also considered for comparative purposes.

Finally, the Deployment phase culminates in a user-friendly Streamlit dashboard. This dashboard allows stakeholders to interactively explore forecasts by selecting specific stores and product families. It features visualizations of historical and predicted sales, confidence intervals, and promotional indicators. The final application is deployed on Render, enabling public access and demonstration of the project's value.

## Exploratory Data Insights

---> COMING SOON! 
## Modeling and Evaluation

---> COMING SOON! 
## Conclusion and Future Work

---> COMING SOON! 
## Technical Installation / Usage Guide

To run this project locally, start by cloning the repository using:

````
bash 
git clone https://github.com/D0bledore/store-sales-time-series-forecasting.git 
cd store-sales-time-series-forecasting
```
````

Create a virtual environment and install dependencies:

````

python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```
````

Launch Jupyter Notebook for exploration:

```

jupyter notebook
```

To run the Streamlit dashboard locally:

```
streamlit run app.py
```

The dashboard is also deployed on Render. Visit the provided deployment URL to view the interactive application. 
- URL ---> COMING SOON! 

## Credits and Acknowledgements

The dataset for this project is provided by the Kaggle competition [Store Sales - Time Series Forecasting]([https://www.kaggle.com/competitions/store-sales-time-series-forecasting/data](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/data)). This project structure and documentation align with the Code Institute's Predictive Analytics assessment guidelines. Core libraries used include pandas, numpy, matplotlib, seaborn, scikit-learn, XGBoost, LightGBM, Prophet, Streamlit, and statsmodels.
