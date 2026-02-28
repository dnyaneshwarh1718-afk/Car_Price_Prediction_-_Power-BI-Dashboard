# 🚗 Car Price Prediction Model — Power BI Dashboard

> A multi-page interactive Power BI report that combines **exploratory data analysis** with **machine learning price predictions** across 1,610 car listings from 2023–2024.

---

## 📌 Project Overview

This Power BI dashboard visualizes automotive pricing data and evaluates a machine learning model's ability to predict car MSRP values. It allows users to explore pricing trends by brand, body style, drivetrain, engine aspiration, and performance metrics like horsepower and torque.

---

## 📂 Dataset

| Property | Details |
|---|---|
| **File** | `Car_Data_with_pred.xlsx` |
| **Records** | 1,610 vehicles |
| **Year Range** | 2023 – 2024 |
| **Source** | Automotive market listings |

### Columns Used

| Column | Type | Description |
|---|---|---|
| `Make` | Dimension | Car brand (Ford, BMW, Audi, etc.) |
| `Model` | Dimension | Car model name |
| `Year` | Dimension | Model year (2023 / 2024) |
| `Trim` | Dimension | Variant / package |
| `Body Style` | Dimension | SUV, Sedan, Pickup Truck, Coupe, etc. |
| `Body Size` | Dimension | Compact / Midsize / Large |
| `Drivetrain` | Dimension | AWD / RWD / FWD / 4WD |
| `Transmission` | Dimension | Automatic / Manual |
| `Engine Aspiration` | Dimension | Turbocharged / Twin-Turbo / NA / Electric |
| `MSRP` | Measure | Actual manufacturer suggested retail price |
| `Used/New Price` | Measure | Market listing price |
| `MSRP Predictions` | ML Output | ML model predicted price |
| `Horsepower_No` | Numeric | Numeric horsepower value |
| `Torque_No` | Numeric | Numeric torque value |

---

## 📊 Dashboard Pages

### Page 1 — Main Dashboard (`Car Price Prediction Model`)

An executive-level overview of the full dataset with interactive slicers and 5 key visualizations.

**KPI Cards (Header Row)**
- 🔢 **Number of Cars** — 1,610 total listings
- 💰 **Average MSRP** — $72.54K
- 🤖 **Average Predicted MSRP** — $72.17K

**Charts**
| Visual | Description |
|---|---|
| Bar Chart | Number of Cars by Make — ranked from Ford (626) to Aston Martin (9) |
| Line Chart | MSRP vs MSRP Predictions by Model — dual-line comparison across all models |
| Line Chart | MSRP vs MSRP Predictions by Make — brand-level actual vs predicted |
| Scatter Plot | MSRP vs Horsepower — correlation analysis with trend line |
| Scatter Plot | MSRP vs Torque — correlation analysis with trend line |

**Slicers / Filters**
- Model (dropdown)
- Make (button chips — Aston Martin, Audi, Bentley...)
- Body Size (Compact / Large / Midsize)
- Body Style (Cargo Minivan, Cargo Van, Convertible...)

---

### Page 2 — Vehicle Records (`Car Vehicle Records — Price vs. Prediction`)

A detailed drill-down table showing individual vehicle records with conditional formatting.

**Features**
- 📋 Full data table: Make, Model, Body Style, Engine Aspiration, Drivetrain, MSRP, MSRP Predictions, Variance %
- 🟢🔴 **Conditional Formatting** on Variance % — Green = model overestimated (prediction > actual), Red = model underestimated
- 🎚️ **Price Range Slider** — filter by Used/New Price ($15,980 – $391,100)
- 🔙 **"Report view"** navigation button to return to main dashboard

---

## 📐 Key Metrics & Insights

| Metric | Value |
|---|---|
| Total Listings | 1,610 |
| Average MSRP | $72,540 |
| Average Predicted MSRP | $72,170 |
| Min MSRP | $15,980 (Ford) |
| Max MSRP | $391,100 (Bentley) |
| Most Listed Brand | Ford — 626 models |
| Avg Horsepower | 346 hp |
| HP Range | 122 – 831 hp |
| Most Common Body Style | SUV (480 listings) |
| Most Common Drivetrain | AWD (757 listings) |
| Automatic Transmission | 97% of listings |

---

## 🤖 Machine Learning Model

The dataset includes pre-generated MSRP predictions from a regression model stored in the `MSRP Predictions` column.

**Model Performance (DAX-calculated)**

```dax
-- Average Prediction Error %
Avg Error % = 
AVERAGEX(
    'Car_Data_with_pred',
    ABS([MSRP] - [MSRP Predictions]) / [MSRP] * 100
)

-- Variance %
Variance % = 
([MSRP Predictions] - [MSRP]) / [MSRP] * 100
```

| Metric | Value |
|---|---|
| Estimated R² Score | ~0.891 |
| Avg Absolute Error | ~$4,200 |
| Prediction Direction | Model slightly underestimates on average |

---

## 🎨 Theme & Design

- **Color Theme**: Custom dark theme — `CarsNeonDark_Theme.json`
- **Background**: `#080b12` (deep dark navy)
- **Card Background**: `#0d1117`
- **Primary Accent**: `#00d4ff` (cyan)
- **Secondary Accent**: `#ff3c6e` (red-pink)
- **Positive Indicator**: `#00e5a0` (green)
- **Negative Indicator**: `#ff3c6e` (red)
- **Data Color Palette**: Cyan → Pink → Gold → Green → Purple → Orange

To apply the theme in Power BI:
> **View → Themes → Browse for themes → select `CarsNeonDark_Theme.json`**

---

## 🗂️ File Structure

```
📁 Car-Price-Prediction-Dashboard/
├── 📊 Car_Price_Prediction_Model.pbix     # Power BI report file
├── 📄 Car_Data_with_pred.xlsx             # Source dataset
├── 🎨 CarsNeonDark_Theme.json             # Custom Power BI theme
└── 📖 README.md                           # This file
```

---

## 🚀 How to Use

1. **Clone or download** this repository
2. Open `Car_Price_Prediction_Model.pbix` in **Power BI Desktop**
3. If data doesn't load, go to **Home → Transform Data → Data Source Settings** and repoint to `Car_Data_with_pred.xlsx`
4. Apply the theme: **View → Themes → Browse for themes → `CarsNeonDark_Theme.json`**
5. Use slicers on Page 1 to filter by Make, Body Style, or Size
6. Click **"Report view"** button to navigate to the detailed records table on Page 2
7. Use the **price range slider** on Page 2 to filter by budget

---

## 🔧 Requirements

| Tool | Version |
|---|---|
| Power BI Desktop | Latest (free) |
| Microsoft Excel | For viewing source data |
| Windows OS | Required for Power BI Desktop |

---

## 📈 Future Improvements

- [ ] Add Year slicer (2023 vs 2024 toggle)
- [ ] Add ML Accuracy KPI card (Avg Error %)
- [ ] Add Buyer Explorer page with budget range filter
- [ ] Add Donut chart for body style distribution
- [ ] Rewrite chart titles to insight-driven format
- [ ] Add custom drill-through tooltip pages
- [ ] Add 2023 vs 2024 year-over-year comparison page

---

## 👤 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/dnyaneshwarh1718-afk)
- LinkedIn: [Your LinkedIn](www.linkedin.com/in/dnyaneshwar-hiwale-27a5a2192)
