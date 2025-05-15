# Filtering, Sorting & Grouping

## Finding Patterns in Data

### Learning Objectives

You will:

* Use Pandas to filter rows using conditions
* Sort data by one or more columns
* Group data to discover trends and totals
* Reinforce understanding through six tasks
* Continue documenting and committing your code to GitHub

***

**Work through each task below. After each one, commit your code and reflection to GitHub.**

***

### 📂 Prerequisites

* Make sure your GitHub repo is pulled and up to date
* Your dataset (`athlete_events.csv`) is in the same folder as your `main.py`

***

### 🧪 Task 1: Filtering Basics

## 🧪 Week 3: Filtering, Sorting & Grouping – Finding Patterns in Data

### 🎯 Learning Objectives

You will:

* Use Pandas to filter rows using conditions
* Sort data by one or more columns
* Group data to discover trends and totals
* Reinforce understanding through six tasks
* Continue documenting and committing your code to GitHub

***

### ⏱️ Estimated Time: 3 Hours

**Work through each task below. After each one, commit your code and reflection to GitHub.**

***

### 📂 Prerequisites

* Make sure your GitHub repo is pulled and up to date
* Your dataset (`athlete_events.csv`) is in the same folder as your `main.py`

***

### Task 1: Filtering Basics

```python
# Filter for female athletes only
female_athletes = df[df['Sex'] == 'F']
print(female_athletes.head())

# Filter for athletes older than 35
older_athletes = df[df['Age'] > 35]
print(older_athletes[['Name', 'Age', 'Sport']].head())
```

**Reflect**:

* What do these filters do?
* How many rows were returned? Use `len()`.

### Task 2: Combine Filters

```python
# Female athletes over 30
combo_filter = df[(df['Sex'] == 'F') & (df['Age'] > 30)]
print(combo_filter[['Name', 'Age', 'Sport']].head())

# Male athletes in Basketball
basketball_males = df[(df['Sex'] == 'M') & (df['Sport'] == 'Basketball')]
print(basketball_males.head())
```

Create a new filter

* Write a filter for athletes from **Australia** in **Swimming**

### Task 3: Sorting Data

```python
# Sort by age
sorted_by_age = df.sort_values(by='Age', ascending=False)
print(sorted_by_age[['Name', 'Age', 'Sport']].head())

# Sort by weight
sorted_by_weight = df.sort_values(by='Weight', ascending=False)
print(sorted_by_weight[['Name', 'Weight', 'Sport']].head())
```

**Apply the skill**

* Sort by **Height then Weight** and display top 10.

### Task 4: Grouping Data

```python
# Count participants in each sport
sport_counts = df['Sport'].value_counts()
print(sport_counts.head())

# Count medals per team
medals_by_team = df[df['Medal'].notnull()].groupby('Team')['Medal'].count()
print(medals_by_team.sort_values(ascending=False).head())
```

**Apply the skill**

* Which **sport** had the most **female** participants?

