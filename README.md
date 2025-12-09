# End-to-End-Insurance-Risk-Analytic

# 📌 Project README

## 📖 Overview

This repository contains the full workflow for **data cleaning, exploratory data analysis (EDA), sentiment preparation, and database integration** for the Bank Reviews Analysis Project.

The project uses **Python, DVC, PostgreSQL, and data science tools** to process raw customer reviews, clean them, generate insights, and prepare the data for modeling.

---

## 🗂️ Repository Structure

```
├── data/
│   ├── .gitignore                  
│   ├── MachineLearningRating_v3.txt         
│   └── MachineLearningRating_v3.txt.dvc            
│
├── notebooks/ eda.ipynb                # Jupyter notebooks for EDA
│
│
├── dvc.yaml                  # DVC pipeline configuration
├── requirements.txt          # Python package dependencies
└── README.md                 # Documentation
```

---

## 🚀 Features

### ✔ Data Cleaning

* Handles numeric values with commas like `'285700,00'`
* Converts text-based numbers to float
* Removes duplicates & missing values
* Outputs a fully cleaned file: `processed_data.txt`

### ✔ Exploratory Data Analysis (EDA)

* Summary statistics
* Distribution plots
* Correlation heatmaps
* Outlier visualizations

### ✔ DVC Pipeline

* Tracks data dependencies
* Ensures reproducible data flow
* Manages versioning of datasets

### ✔ Database Integration

* PostgreSQL connection using `psycopg2` or `SQLAlchemy`
* Creates tables: **Banks**, **Reviews**
* Inserts cleaned review data
* Performs validation queries

---

## 🛠️ Installation

### 1️⃣ Clone the Repository

```
git clone <your_repo_url>
cd <repo_name>
```

### 2️⃣ Create a Virtual Environment

```
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
```

### 3️⃣ Install Dependencies

```
pip install -r requirements.txt
```

### Common Libraries Used:

* pandas
* numpy
* matplotlib
* seaborn
* dvc

---

## ▶️ Usage

### **Run the full DVC pipeline:**

```
dvc repro
```

### **Step-by-step Execution:**

#### Clean Data

```
python scripts/clean_data.py
```

#### Run EDA

```
python scripts/eda.py
```

#### Load into PostgreSQL

```
python scripts/load_to_db.py
```

---

## 🧪 Example Fixes Implemented

### 🟦 Issue: `ValueError: could not convert string to float: '285700,00'`

**Fix:**

```python
df['amount'] = df['amount'].str.replace(',', '.').astype(float)
```

### 🟦 Issue: DVC Error – `processed_data.txt` missing

**Fix:** ensured cleaning script always writes output into `data/processed/`.

---

## 📊 Outputs

* Cleaned dataset: `data/processed/processed_data.txt`
* EDA visualizations: `notebooks/` or `plots/`
* Database-ready table inserts

---

## 🧩 Next Steps

* Apply NLP preprocessing for sentiment analysis
* Train ML models on review text
* Build dashboard for insights (Streamlit / PowerBI)

---

## 👤 Author

**Sophonias Tamene**
Machine Learning & Data Engineering Trainee

---

