# big-data-project-uber-powerbi


# 🎯 Uber Fares Dataset Analysis (Big Data Project)

> A complete data analysis project for **INSY 8413 – Introduction to Big Data Analytics** using **Python (Pandas)** and **Power BI**

![Tool](https://img.shields.io/badge/Tool-Python%20%7C%20Power%20BI-brightgreen)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle%20Uber%20Fares-blue)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

## 📘 Project Overview

This project analyzes the **Uber Fares dataset** using Python (Pandas) and builds an interactive dashboard in **Power BI** to reveal fare patterns, trip characteristics, and temporal trends. The dataset contains **200,000+ records** of ride information including pickup/dropoff locations, fare amounts, and timestamps.

---

## ⚖️ Assignment Objective (per Instructor)

> Analyze the Uber Fares Dataset to gain comprehensive insights into fare patterns, ride durations, and key operational metrics. Students will:

* Perform EDA using Python
* Clean and preprocess the data
* Engineer analytical features
* Import the enhanced dataset into **Power BI**
* Build a complete interactive dashboard
* Present findings through a **detailed analytical report**

---

## 🛠️ Tools & Technologies

| Tool              | Purpose                            |
| ----------------- | ---------------------------------- |
| ⚪ Python (Pandas) | Data cleaning and feature creation |
| 🔹 Google Colab   | Cloud-based Python notebook        |
| 💡 Power BI       | Data visualization and dashboard   |
| 💾 GitHub         | Submission & documentation         |

---

## 📊 Data Understanding & Initial Inspection

### ✅ Step 1: Dataset Upload and Structure Check

* Loaded the `uber.csv` file into Pandas
* Inspected the first 5 rows to understand the schema
* Identified 9 columns including coordinates, fare, time, and passengers

```python
import pandas as pd
df = pd.read_csv('uber.csv')
df.head()
```

**📸 Screenshot:**
<img width="1920" height="982" alt="image" src="https://github.com/user-attachments/assets/90336f78-58a7-4eca-9366-250c92ca3e21" />


### ✅ Step 2: Check Shape, Data Types, Missing Values

```python
print(df.shape)
print(df.dtypes)
print(df.isnull().sum())
```

* Total Rows: 200,000
* Detected 1 missing value each in `dropoff_latitude` and `dropoff_longitude`
* Noticed `pickup_datetime` was not in datetime format

**📸 Screenshot:**
<img width="1920" height="832" alt="image" src="https://github.com/user-attachments/assets/557cc93c-efeb-4113-882f-fc855c22c808" />


### ✅ Step 3: Descriptive Statistics

```python
df.describe()
```

* Found negative or zero fare values
* Passenger count outliers (0, very high values)

**📸 Screenshot:**
<img width="1920" height="787" alt="image" src="https://github.com/user-attachments/assets/67b36b74-d359-40b7-a0cc-1e3a974b184f" />


---

## 🦜 Data Cleaning

### ✅ Step 4: Clean and Prepare Data

```python
# Drop unnamed index column
# Convert pickup_datetime
# Drop nulls
# Filter invalid fare_amount and passenger_count

...
```

**Key Cleaning Actions:**

* Dropped `Unnamed: 0` (useless index)
* Converted `pickup_datetime` to proper datetime format
* Dropped 2 null rows
* Removed trips with fare ≤ 0 and passenger count < 1 or > 6

**📸 Screenshot:**
<img width="1920" height="814" alt="image" src="https://github.com/user-attachments/assets/cece6a2f-f61e-4d99-a1ba-b883760d7664" />


### ✅ Step 5: Check Final Dataset Shape

```python
print(df.shape)
```

**📈 Final Shape: 199,268 rows × 8 columns**

---

## 🧠 Feature Engineering

### ✅ Step 6: Create New Analytical Columns

```python
df['hour'] = df['pickup_datetime'].dt.hour
...
```

* Extracted hour, day, month, weekday
* Created `is_weekend` boolean feature

**📸 Screenshot:**
![Feature Engineering](./screenshots/5_feature_engineering_preview.png)

---

## 💾 Export to CSV for Power BI

### ✅ Step 7: Save Enhanced Dataset

```python
df.to_csv('uber_cleaned.csv', index=False)
```

* Downloaded the final cleaned file
* Ready to import into Power BI for visual analysis

**📸 Screenshot:**
![CSV Export](./screenshots/6_csv_download.png)

---

## 📊 Next Steps (Power BI Dashboard)

1. Import `uber_cleaned.csv` into Power BI
2. Create time-based visualizations:

   * Hourly fare patterns
   * Day vs weekend fare comparison
   * Monthly trends
3. Build an interactive dashboard with filters
4. Export `.pbix` file and screenshots

---

## 📝 Report & Submission Requirements

| Deliverable               | Format                     |
| ------------------------- | -------------------------- |
| Cleaned Dataset           | `uber_cleaned.csv`         |
| Dashboard                 | `uber_dashboard.pbix`      |
| Documentation Screenshots | `/screenshots/*.png`       |
| Final Report              | `README.md` (this file)    |
| GitHub Repository         | Public repo with all files |

---

## 👨‍💻 Author

**Jospin Nabonyimana**
🎓 Student, Adventist University of Central Africa
📈 Course: INSY 8413 – Introduction to Big Data Analytics
📧 Email: [your-email@example.com](mailto:your-email@example.com)
