# Correlation and Deeper Analysis

### Health Data

Use this data set for this new project. Create a new repository and new `main.py` file

{% file src="../.gitbook/assets/gym_members_exercise_tracking.csv" %}

**Learning Objectives:**

* Understand and calculate **correlations** between numerical fields
* Explore more advanced visualisations (e.g. scatter plots, heatmaps)
* Interpret relationships and patterns in the data

***

#### Task 1: Correlation Matrix

```python
# Show correlation between numerical columns
correlation = df.corr(numeric_only=True)
print(correlation)
```

✅ Challenge: Which two variables are most strongly correlated? Which are surprisingly not?

***

#### Task 2: Scatter Plot to Explore Relationships

```python
# Scatter plot: Steps vs Calories
df.plot.scatter(x='Steps', y='Calories', title='Steps vs Calories')
plt.tight_layout()
plt.savefig('scatter_steps_calories.png')
plt.show()
```

✅ Try plotting:

* Sleep Hours vs Resting Heart Rate
* Distance vs Active Minutes

📝 Write a sentence describing what you observe in each.

***

#### Task 3: Create a Custom Metric or Column

```python
# Example: Steps per minute of active time
df['StepsPerActiveMin'] = df['Steps'] / df['ActiveMinutes']
print(df[['Steps', 'ActiveMinutes', 'StepsPerActiveMin']].head())
```

✅ Invent your own simple health-related metric. What does it help reveal?

***

**Task 4: Reflection**

* Which analysis this week was most meaningful?
* Which correlations surprised you?
* What questions still remain unanswered in this dataset?

✅ Write these in your GitBook or project journal

***

### ✅ Week 10 Checklist

* [ ] Calculated correlation matrix
* [ ] Plotted and analysed at least two scatter plots
* [ ] Created a custom metric or column
* [ ] Reflected on key insights
* [ ] Committed changes and visuals to GitHub
