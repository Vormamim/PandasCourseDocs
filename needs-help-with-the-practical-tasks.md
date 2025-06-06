---
icon: hands-holding-heart
---

# Needs help with the practical Tasks?

## 🏋️Olympic Athlete Data Analysis

Needs some help with the TASKS? Here's some juicy clues.

***

<details>

<summary>Help me! - Open if you need a few more tips</summary>

### 📁 Getting Started

```python
import pandas as pd

df = pd.read_csv('athlete_events.csv')
```

***

### ✅ Task 1: Filtering Basics

#### 1. Filter for female athletes only

```python
female_athletes = df[df['Sex'] == 'F']
print(female_athletes.head())
print("Total rows:", len(female_athletes))
```

* This selects only the rows where the value in the `Sex` column is `'F'`.

#### 2. Filter for athletes older than 35

```python
older_athletes = df[df['Age'] > 35]
print(older_athletes[['Name', 'Age', 'Sport']].head())
print("Total rows:", len(older_athletes))
```

* Filters athletes where the `Age` column is greater than 35.

***

### ✅ Task 2: Combine Filters

#### 1. Female athletes over 30

```python
combo_filter = df[(df['Sex'] == 'F') & (df['Age'] > 30)]
print(combo_filter[['Name', 'Age', 'Sport']].head())
print("Total rows:", len(combo_filter))
```

* Combines two conditions using `&` to filter female athletes over age 30.

#### 2. Male athletes in Basketball

```python
basketball_males = df[(df['Sex'] == 'M') & (df['Sport'] == 'Basketball')]
print(basketball_males.head())
print("Total rows:", len(basketball_males))
```

#### 3. Australian athletes in Swimming (custom task)

```python
aus_swimmers = df[(df['Team'] == 'Australia') & (df['Sport'] == 'Swimming')]
print(aus_swimmers[['Name', 'Age', 'Sex']].head())
print("Total rows:", len(aus_swimmers))
```

***

### ✅ Task 3: Sorting Data

#### 1. Sort by age (descending)

```python
sorted_by_age = df.sort_values(by='Age', ascending=False)
print(sorted_by_age[['Name', 'Age', 'Sport']].head())
```

#### 2. Sort by weight (descending)

```python
sorted_by_weight = df.sort_values(by='Weight', ascending=False)
print(sorted_by_weight[['Name', 'Weight', 'Sport']].head())
```

#### 3. Sort by height, then weight (descending)

```python
sorted_height_weight = df.sort_values(by=['Height', 'Weight'], ascending=False)
print(sorted_height_weight[['Name', 'Height', 'Weight']].head(10))
```

***

### ✅ Task 4: Grouping Data

#### 1. Count participants in each sport

```python
sport_counts = df['Sport'].value_counts()
print(sport_counts.head())
```

#### 2. Count medals per team

```python
medals_by_team = df[df['Medal'].notnull()].groupby('Team')['Medal'].count()
print(medals_by_team.sort_values(ascending=False).head())
```

#### 3. Sport with most female participants

```python
female_sport_counts = df[df['Sex'] == 'F']['Sport'].value_counts()
print(female_sport_counts.head(1))
```

***

### ✅ Task 5: Aggregating with groupby()

#### 1. Average height per sport

```python
avg_height = df.groupby('Sport')['Height'].mean().sort_values(ascending=False)
print(avg_height.head())
```

#### 2. Median age by year

```python
median_age_by_year = df.groupby('Year')['Age'].median()
print(median_age_by_year.tail())
```

#### 3. Average weight by sex and sport

```python
avg_weight_sex_sport = df.groupby(['Sex', 'Sport'])['Weight'].mean().sort_values(ascending=False)
print(avg_weight_sex_sport.head(10))
```

***

### ✅ Task 6: Exporting a Subset

#### Export Gymnastics athletes to a CSV

```python
gymnasts = df[df['Sport'] == 'Gymnastics']
gymnasts.to_csv('gymnastics_athletes.csv', index=False)
print("Exported to gymnastics_athletes.csv")
```

***

### ✅ Recap

You now know how to:

* Use **filters** to **select rows**
* **Combine** conditions using logical operators
* Sort data by multiple columns
* Group and aggregate information
* Export a subset of your DataFrame

Happy coding! 🐼

</details>
