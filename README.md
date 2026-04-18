# Airbnb Open Data Cleaning Project

## Overview

This project focuses on cleaning and transforming the **Airbnb Open Data** dataset using **Python (Pandas)** in Jupyter Notebook.

Raw datasets often contain missing values, duplicate records, inconsistent formatting, unnecessary columns, and incorrect data types. This notebook demonstrates how to clean such data and prepare it for analysis or machine learning.

## Objective

The main goal of this project is to convert raw Airbnb listing data into a structured, clean, and analysis-ready dataset.

## Tools & Technologies Used

* Python
* Jupyter Notebook
* Pandas Library

## Dataset Used

**File Name:** `Airbnb_Open_Data.csv`

The dataset contains Airbnb property listing details such as:

* Property Name
* Host ID
* Host Name
* Verification Status
* Location Details
* Room Type
* Price
* Service Fee
* Number of Reviews
* Cancellation Policy
* Construction Year
* Booking Availability

## Data Cleaning Steps Performed

### 1️⃣ Import Required Library

```python
import pandas as pd
```

### 2️⃣ Load Dataset

```python
df = pd.read_csv("Airbnb_Open_Data.csv")
```

### 3️⃣ Select Important Columns

Kept only useful columns for analysis and removed irrelevant columns.

Examples of selected columns:

* NAME
* host id
* host name
* neighbourhood
* room type
* price
* service fee
* number of reviews

### 4️⃣ Drop Unnecessary Columns

Removed columns such as:

* reviews per month
* availability 365
* house_rules
* license
* id

### 5️⃣ Rename Columns

Example:

```python
df.rename(columns={'NAME':'Name'}, inplace=True)
```

### 6️⃣ Convert Column Names to Uppercase

Standardized all column names.

### 7️⃣ Remove Duplicate Records

```python
df.drop_duplicates(inplace=True)
```

### 8️⃣ Handle Missing Values

Checked null values and removed rows containing missing data.

```python
df.dropna(inplace=True)
```

### 9️⃣ Standardize Text Data

Converted values to uppercase.

Example:

```python
df['host_identity_verified'] = df['host_identity_verified'].str.upper()
```

### 🔟 Convert Boolean to Numeric

Changed `True/False` values into `1/0`

```python
df['instant_bookable'] = df['instant_bookable'].apply(lambda x: 1 if x == True else 0)
```

### 1️⃣1️⃣ Clean Price Column

Removed:

* Dollar sign `$`
* Commas `,`
* Extra spaces

Converted text values into integers.

```python
df['price'] = df['price'].astype(int)
```

### 1️⃣2️⃣ Reset Index

```python
df.reset_index(inplace=True)
```

### 1️⃣3️⃣ Export Cleaned Dataset

```python
df.to_csv("Cleaned_data.csv", index=False)
```

## Skills Demonstrated

* Data Cleaning
* Data Transformation
* Feature Preparation
* Handling Missing Values
* Duplicate Removal
* Data Type Conversion
* Text Standardization
* Exporting Data

## Tags

`Python` `Pandas` `Data Cleaning` `Jupyter Notebook` `Airbnb Dataset` `Data Analysis`
