# Implementing the Project

## Start Building

### Learning Objectives

You will:

* Begin implementing your own data analysis project using Pandas
* Apply filters, grouping, and visualisation techniques to your dataset
* Document your progress in a project notebook or GitBook
* Commit each functional milestone to GitHub

***

Complete each of the five tasks below. These form the **foundation of your final project**.

***

### 📂 Prerequisites

* You've defined your project question, requirements, and test cases (Week 6)
* Your cleaned dataset `athlete_events_cleaned.csv` is in the project folder
* Your repository is **pulled and synced** using GitHub Desktop

***

### Task 1: Start a New Project File

Create a new file in your GitHub repo:

```plaintext
project_analysis.py
```

At the top of the file:

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv("athlete_events_cleaned.csv")

# Confirm loaded
print(df.head())
```

**Commit and Push**: "Started project\_analysis.py and loaded data"

***

### Task 2: Apply Your Project Filters

Use your Week 6 test cases to apply at least one filter. Example:

```python
# Filter for female gymnasts since 1980
filtered_df = df[(df['Sport'] == 'Gymnastics') & (df['Year'] >= 1980) & (df['Sex'] == 'F')]
print(filtered_df.head())
```

Save one result using `len(filtered_df)` to confirm your filter works.

Commit: "Applied initial filters for project"

***

### Task 3: Add a Calculation or Grouping

Now calculate a meaningful statistic:

```python
# Average height by Olympic year
avg_height = filtered_df.groupby('Year')['Height'].mean()
print(avg_height)
```

Choose your own calculation based on your question:

* Count of medals?
* Average age?
* Gender split?

Commit: "Grouped and calculated project metrics"

***

### Task 4: Draft Your First Chart

Visualise the trend you calculated above:

```python
avg_height.plot(kind='line', title='Avg Female Gymnast Height Over Time')
plt.xlabel('Year')
plt.ylabel('Height (cm)')
plt.tight_layout()
plt.savefig("gymnast_height_trend.png")
plt.show()
```

Save your image in the same folder as your script.

Commit: "Drafted first chart"

***

### Task 5: Document Progress and Roadblocks

In your project journal, answer:

* What have you achieved so far?
* Did your filters or calculations work as expected?
* What problem did you encounter, and how did you solve it (or plan to)?

***

### REMINDER: GitHub Workflow

For each task:

* Save your script and chart images
* Write a commit message
* Use GitHub Desktop to **commit and push**

***

### ✅ Week 6.2 Checklist

* [ ] Created `project_analysis.py`
* [ ] Applied filters based on project test cases
* [ ] Grouped or calculated meaningful data
* [ ] Created at least one draft chart
* [ ] Documented progress and challenges
* [ ] Committed all work to GitHub
