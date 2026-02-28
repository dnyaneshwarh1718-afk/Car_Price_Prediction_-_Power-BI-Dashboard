# 🚗 Car Price Prediction + Power BI Dashboard

A end-to-end machine learning project that predicts used car prices using **Linear Regression**, visualizes results through an interactive **Power BI Dashboard**, and deploys a live prediction app via **Streamlit**.

---

## 📌 Project Overview

This project covers the full data science workflow — from data preprocessing and model training to business intelligence reporting and web app deployment. The trained model predicts car prices based on 36 one-hot encoded features, with predictions exported to Excel for Power BI visualization and the model serialized as a `.pkl` file for Streamlit deployment.

---

## 📊 Model Performance

| Metric | Value |
|--------|-------|
| R² Score | **0.92** |
| RMSE | **$16,534** |
| Algorithm | Linear Regression |
| Features | 36 (One-Hot Encoded) |

---

## 🗂️ Project Structure

```
Car_Price_Prediction_-_Power-BI-Dashboard/
│
├── Streamlit car price prediction .ipynb   # Jupyter notebook: EDA, preprocessing, model training
├── Car_price.py                            # Streamlit app for live car price prediction
├── linear_model.pkl                        # Saved trained Linear Regression model
├── Car_Data_with_pred.xlsx                 # Dataset with actual vs predicted prices (for Power BI)
├── Pic 1.PNG                               # sample iamge 
├── Pic 2.PNG                               # sample iamge 
└── README.md
```

---

## ⚙️ Tech Stack

- **Python** — Data processing & model training
- **Pandas / NumPy** — Data manipulation
- **Scikit-learn** — Linear Regression, One-Hot Encoding, train-test split
- **Pickle** — Model serialization (`.pkl`)
- **Jupyter Notebook** — Exploratory Data Analysis (EDA) & model development
- **Microsoft Power BI** — Interactive dashboard for predictions & insights
- **Streamlit** — Web app for real-time car price prediction

---

## 🔄 Workflow

```
Raw Car Data
    ↓
EDA & Feature Engineering (Jupyter Notebook)
    ↓
One-Hot Encoding (36 features)
    ↓
Train Linear Regression Model
    ↓
Evaluate: R² = 0.92 | RMSE = $16,534
    ↓
   ┌────────────────────────────────┐
   │                                │
Export predictions to Excel     Save model as .pkl
(Car_Data_with_pred.xlsx)       (linear_model.pkl)
   │                                │
Power BI Dashboard            Streamlit Web App
```

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy scikit-learn streamlit joblib openpyxl
```

### Run the Streamlit App

```bash
streamlit run Car_price.py
```

The app will open in your browser at `http://localhost:8501`, where you can input car details and get an instant price prediction.

### Run the Notebook

Open `Streamlit car price prediction .ipynb` in Jupyter Notebook or JupyterLab to explore the data analysis and model training process step by step.

---

## 📈 Power BI Dashboard

The `Car_Data_with_pred.xlsx` file contains both actual and predicted car prices and is used as the data source for the Power BI Dashboard. The dashboard provides:

- Actual vs. Predicted price comparisons
- Price distribution by car brand, year, fuel type, and transmission
- Key metrics and KPIs at a glance


---

## 🧠 Feature Engineering

The dataset was preprocessed using **One-Hot Encoding** to convert categorical variables (such as car brand, fuel type, transmission, and Drivetrain) into numerical features, resulting in **36 features** used for model training.

---

## 📁 Key Files

- **`linear_model.pkl`** — Pre-trained model. Load it directly to make predictions without retraining:
  ```python
  import joblib
  model = joblib.load('linear_model.pkl')
  prediction = model.predict(your_feature_array)
  ```

- **`Car_Data_with_pred.xlsx`** — Ready-to-use Excel file for importing into Power BI.

---

## 👤 Author

**Dnyaneshwar H.**  
[GitHub Profile](https://github.com/dnyaneshwarh1718-afk)



