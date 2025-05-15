# Data Cleaning – Preparing Messy Data

This week builds skills in identifying, cleaning, and preparing real-world data for analysis using the same `athlete_events.csv` dataset.

### Learning Objectives

You will:

* Identify missing, null, and inconsistent data
* Use Pandas to clean and fill missing values
* Drop or replace incorrect data
* Validate your dataset for analysis
* Save a clean version for your project work

***

### ⏱️ Estimated Time: 3 Hours

Work through the **six scaffolded tasks**, committing after each one to your GitHub repo.

***

### 📂 Prerequisites

* Confirm your `main.py` file is working
* You’re using the `athlete_events.csv` dataset
* You've pulled the latest code from GitHub

***

&#x20;Task 1: Check for Missing Data

```python
# Count missing values in each column
print(df.isnull().sum())
```

* Which **3 columns** have the most missing values?
* Why might this happen in real-world Olympic data?

> 💡 Tip: Look at `Height`, `Weight`, and `Medal`.

***

Task 2: Drop Rows with Critical Missing Data

```python
# Drop rows missing both height and weight
df_cleaned = df.dropna(subset=['Height', 'Weight'])
print(df_cleaned.shape)
```

Challenge:

* How many rows did you remove?
* What are the pros and cons of dropping data?

***

Task 3: Fill Missing Values (e.g. 'Medal')

```python
# Fill missing medals with 'None'
df_cleaned['Medal'] = df_cleaned['Medal'].fillna('None')

# Fill missing ages with average age
avg_age = df_cleaned['Age'].mean()
df_cleaned['Age'] = df_cleaned['Age'].fillna(avg_age)
```

Try:

* Replace missing **Weight** with average weight
* Use `.median()` instead of `.mean()` and compare

***

Task 4: Detect Inconsistent Data

```python
# Unique values in 'Sex' and 'Medal'
print(df_cleaned['Sex'].unique())
print(df_cleaned['Medal'].unique()) Look for:
```

* Extra spaces or capitalisation issues
* Typos or strange values

If needed:

```python
# Strip whitespace from strings
df_cleaned['Medal'] = df_cleaned['Medal'].str.strip()
```

***

Task 5: Validate and Describe Cleaned Data

```python
# Check again for missing values
print(df_cleaned.isnull().sum())

# Get stats after cleaning
print(df_cleaned.describe())
```

Reflection:

* Did cleaning improve the dataset?
* What questions could now be answered more confidently?

***

Task 6: Save the Clean Dataset

```python
# Save your cleaned version
df_cleaned.to_csv("athlete_events_cleaned.csv", index=False)
```

Check:

* Open the CSV in Excel or Sheets
* Is it readable, complete, and useful?

***

### 📚 Reflection Journal

Answer in your journal

1. What was the **dirtiest** column in the dataset?
2. How did you decide when to drop vs fix missing data?
3. Why is **data cleaning so important** in real-world projects?

***

### REMINDER: Push After Each Task

After **each task**:

* Save `main.py`
* Open GitHub Desktop
* Write a clear commit message (e.g. "Dropped null rows, filled missing medals")
* Click **Commit to main**, then **Push origin**

***

### ✅ Week 4 Checklist

* [ ] Identified missing and inconsistent values
* [ ] Dropped or filled missing data appropriately
* [ ] Cleaned and validated key columns
* [ ] Saved a new clean version of the dataset
* [ ] Completed journal reflections
* [ ] Pushed all updates to GitHub

