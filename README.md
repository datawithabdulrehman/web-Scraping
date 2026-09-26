# 🚗 PakWheels Used Cars Dataset — Pakistan

> **A large-scale Pakistani used-car dataset collected from publicly accessible PakWheels vehicle listings for Data Science, EDA, visualization, and Machine Learning projects.**

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Data_Processing-013243?logo=numpy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-76B7B2)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Regression-green)

---

## 📌 Overview

The **PakWheels Used Cars Dataset** contains used-car listing information from Pakistan's automotive marketplace.

The dataset was collected and processed for practical **Data Science and Machine Learning** applications.

It includes information about:

* 🚘 Car brands and models
* 📅 Manufacturing year
* ⚙️ Engine capacity
* 🛣️ Mileage
* ⛽ Fuel type
* 🔄 Transmission
* 💰 Price in Pakistani Rupees
* 📊 Derived vehicle age
* 💵 Price in millions of PKR

The dataset can be used for **Exploratory Data Analysis (EDA), Data Visualization, Feature Engineering, Regression, and Used Car Price Prediction**.

---

# 📊 Dataset Information

### Main Features

| Column          | Description                          |
| --------------- | ------------------------------------ |
| `brand`         | Vehicle manufacturer/brand           |
| `name`          | Vehicle model/listing name           |
| `year`          | Vehicle manufacturing/model year     |
| `vehicle_age`   | Approximate age of the vehicle       |
| `fuel_type`     | Fuel type                            |
| `transmission`  | Transmission type                    |
| `engine`        | Original engine capacity information |
| `engine_cc`     | Numeric engine capacity in CC        |
| `mileage`       | Original mileage information         |
| `mileage_km`    | Numeric mileage in kilometers        |
| `price`         | Listed price in PKR                  |
| `price_million` | Price converted to millions of PKR   |
| `currency`      | Listing currency                     |
| `image`         | Vehicle image URL                    |
| `description`   | Original listing description         |
| `page`          | Source pagination page               |
| `source_url`    | Source search URL                    |
| `scraped_date`  | Date of data collection              |

---

# 🧹 Data Processing

The raw scraped data was processed using Python and Pandas.

The preprocessing pipeline includes:

```text
Raw Listings
     ↓
JSON-LD Extraction
     ↓
Duplicate Removal
     ↓
Missing Value Analysis
     ↓
Numeric Conversion
     ↓
Price Cleaning
     ↓
Mileage Cleaning
     ↓
Engine Conversion
     ↓
Vehicle Age Feature
     ↓
Price in Million PKR
     ↓
Validation
     ↓
Final Dataset
```

### Cleaning operations

* Removed duplicate records
* Converted price values to numeric format
* Converted mileage to kilometers
* Converted engine capacity to numeric CC
* Converted manufacturing year to numeric
* Created `vehicle_age`
* Created `price_million`
* Standardized text fields
* Checked invalid numerical values
* Performed missing-value analysis

---

# 🔍 Exploratory Data Analysis

The dataset can be explored through:

### Brand Analysis

* Most common car brands
* Brand-wise listing counts
* Average price by brand
* Price ranges by brand

### Price Analysis

* Overall price distribution
* Average vehicle price
* Price variation across brands
* Price vs mileage
* Price vs engine capacity
* Price vs vehicle age

### Vehicle Analysis

* Manufacturing year distribution
* Mileage distribution
* Engine capacity distribution
* Fuel-type distribution
* Transmission distribution

---

# 📈 Machine Learning Applications

The dataset can be used to build a **Used Car Price Prediction** model.

### Target Variable

```python
price
```

or:

```python
price_million
```

### Possible Features

```text
brand
year
vehicle_age
fuel_type
transmission
engine_cc
mileage_km
```

### Possible Algorithms

* Linear Regression
* Ridge Regression
* Lasso Regression
* Decision Tree Regressor
* Random Forest Regressor
* Gradient Boosting
* XGBoost
* LightGBM
* CatBoost

### Evaluation Metrics

* MAE
* MSE
* RMSE
* R² Score

---

# 💡 Example Research Questions

This dataset can help answer questions such as:

1. Which car brands dominate the Pakistani used-car market?
2. How does vehicle age affect used-car prices?
3. How strongly does mileage affect price?
4. Does engine capacity influence vehicle price?
5. Which fuel type is most common?
6. Which transmission type is most common?
7. Which brands have the highest average prices?
8. Which features have the strongest relationship with price?
9. Can Machine Learning accurately predict used-car prices?

---

# 🛠️ Technologies Used

```text
Python
Pandas
NumPy
Matplotlib
Seaborn
BeautifulSoup
Requests
Jupyter Notebook
Machine Learning
```

---

# 📁 Repository Structure

```text
PakWheels-Used-Cars-Dataset/
│
├── data/
│   ├── pakwheels_used_cars_clean.csv
│   └── pakwheels_used_cars_kaggle.csv
│
├── notebooks/
│   └── pakwheels_eda.ipynb
│
├── scripts/
│   └── pakwheels_scraper.py
│
├── README.md
└── requirements.txt
```

---

# 🚀 Getting Started

Clone the repository:

```bash
git clone https://github.com/datawithabdulrehman/PakWheels-Used-Cars-Dataset.git
```

Move into the project:

```bash
cd PakWheels-Used-Cars-Dataset
```

Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn beautifulsoup4 requests jupyter
```

Launch Jupyter:

```bash
jupyter notebook
```

---

# 📊 Basic Dataset Usage

```python
import pandas as pd

df = pd.read_csv(
    "data/pakwheels_used_cars_kaggle.csv"
)

print(df.shape)

display(df.head())

display(df.describe())
```

---

# 📉 Example: Average Price by Brand

```python
brand_prices = (
    df.groupby("brand")["price_million"]
      .mean()
      .sort_values(ascending=False)
)

print(brand_prices.head(15))
```

---

# 📈 Example: Price vs Mileage

```python
import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(12, 6))

sns.scatterplot(
    data=df,
    x="mileage_km",
    y="price_million",
    alpha=0.5
)

plt.title("Used Car Price vs Mileage")

plt.xlabel("Mileage (KM)")

plt.ylabel("Price (Million PKR)")

plt.show()
```

---

# ⚠️ Data & Usage Note

This dataset represents online vehicle listings available at the time of collection.

Vehicle prices, availability, descriptions, and listings may change over time.

The dataset is intended primarily for **educational, analytical, and research purposes**.

The original source of the vehicle listing information is **PakWheels**. Users should review the source website's current terms and conditions before redistributing the data or using it commercially.

---

# 👨‍💻 Author

## Abdul Rehman

**Data Science Student | Aspiring Data Scientist / ML Engineer**

Focused on:

* 🐍 Python
* 📊 Data Science
* 📈 Data Analysis
* 🤖 Machine Learning
* 🧠 Artificial Intelligence
* 📉 Data Visualization
* 🌐 ML Applications
* 🏆 Kaggle Projects

---

# 🌐 Connect With Me

### 💻 GitHub

https://github.com/datawithabdulrehman

### 🏆 Kaggle

https://www.kaggle.com/datawithabxrehman

### 💼 LinkedIn

https://www.linkedin.com/in/datawithabdulrehman

### 🌐 Portfolio

https://datawithabdulrehman.github.io/ABXREHMAN-PORTFOLIO/

---

# ⭐ Support

If you find this dataset useful for your Data Science or Machine Learning project, consider giving the repository a ⭐.

---

## 📜 License

Please refer to the repository's licensing/usage note and the original source's terms before redistributing the scraped dataset.

---

**Built with Python 🐍 | Data → Insights → Machine Learning 🚗📊**
