# Health & Activity Data

#### Objectives:

* Load and explore `health_activity_data.csv`
* Compare structure with previous dataset
* Identify meaningful questions

#### Before starting, create a new project repository in GitHub called `health_data`

#### Step 1: Load and Inspect the Dataset

Create a new python file called `main.py` inside the folder and a `project_log.md` file to record your work.

```python
import pandas as pd

df = pd.read_csv("health_activity_data.csv")
print(df.head())
print(df.columns)
print(df.info())
```

✅ Task: Write down 3 observations about how this dataset is different from `athlete_events.csv`.

***

#### 🔍 Task 2: Data Profiling

```python
print(df.describe())
print(df.isnull().sum())
```

✅ Challenge:

* What are the most complete and incomplete columns?
* What type of data (numerical, categorical, timestamps)?

***

#### 💡 Task 3: Develop 3 Testable Questions

Examples:

* Is there a correlation between sleep and heart rate?
* Do people who walk more have lower resting heart rates?
* Which activity type burns the most calories?

✅ Save questions and predicted results in journal

***

#### Objectives:

* Apply filters, grouping, and plotting to explore one question
* Create at least 2 visualisations

#### 📊 Task 1: Filter and Group

Example:

```python
# Average steps per user
steps_by_user = df.groupby('User_ID')['Steps'].mean()
print(steps_by_user.head())
```

✅ Challenge: Group by `Activity` or `Day` and visualise a trend.

***

#### 📈 Task 2: Create at Least Two Charts

```python
import matplotlib.pyplot as plt

# Histogram of steps
df['Steps'].plot(kind='hist', bins=30, title='Step Count Distribution')
plt.xlabel('Steps')
plt.tight_layout()
plt.savefig("step_distribution.png")
plt.show()
```

###
