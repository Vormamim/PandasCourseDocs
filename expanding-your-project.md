# Expanding Your Project

## Multiple Visualisations and Refined Insights

### Learning Objectives

You will:

* Expand your project code with more filters, groupings, and charts
* Create a minimum of **3 different visualisations**
* Interpret and describe patterns, trends, and outliers
* Begin drafting your results and conclusions

***

### Estimated Time: 3 Hours

Build from the foundations created last week. Complete all five tasks and commit regularly.

***

### Prerequisites

* You have a working `project_analysis.py` script
* Your dataset is clean and filters have been tested
* You’ve committed at least one visualisation to GitHub

***

### Task 1: Add a Second Visualisation

Choose a **different chart type** or question to explore. For example:

```python
# Medal counts by gender
medals_by_sex = df[df['Medal'] != 'None'].groupby('Sex')['Medal'].count()

medals_by_sex.plot(kind='bar', title='Medals by Gender')
plt.ylabel('Number of Medals')
plt.tight_layout()
plt.savefig("medals_by_gender.png")
plt.show()
```

✅ Commit: `"Added chart showing medals by gender"`

***

**Task 2: Add a Categorical Comparison**

Use `groupby()` to compare values across a **category** (e.g. Team, Year, or Sport):

```python
# Average weight by sport
avg_weight = df.groupby('Sport')['Weight'].mean().sort_values(ascending=False).head(10)

avg_weight.plot(kind='barh', title='Top 10 Sports by Average Weight')
plt.tight_layout()
plt.savefig("avg_weight_by_sport.png")
plt.show()
```

✅ Commit: `"Compared average weight by sport in bar chart"`

***

**Task 3: Create a Trend or Timeline Chart**

If your question involves change over time, make a line graph:

```python
# Number of athletes by year
athletes_per_year = df.groupby('Year')['ID'].nunique()

athletes_per_year.plot(kind='line', title='Total Athletes by Olympic Year')
plt.xlabel('Year')
plt.ylabel('Unique Athletes')
plt.tight_layout()
plt.savefig("athletes_by_year.png")
plt.show()
```

✅ Commit: `"Visualised trend of athletes by year"`

***

**Task 4: Add Preliminary Findings**

In your journal, answer:

* What patterns or trends have you discovered so far?
* Do the charts support your project question or raise new questions?
* Is your dataset showing any **unexpected results**?

📝 Example finding:

> “Although the average height of gymnasts increased from 1980 to 2000, it has levelled off in recent years.”

✅ Commit: `"Added interpretation notes to GitBook"`

***

**Task 5: Check Your Progress Against Your Plan**

Compare your current project to your **Week 6 plan**:

* Have you implemented all functional requirements?
* Have you created test cases and met them?
* Do you need to adjust your project question or focus?

Update your plan or write a short note explaining any changes.

✅ Commit: `"Reviewed plan and adjusted scope for project"`

***

### GitHub Best Practice

For every new visualisation or script change:

* Save your Python file and image
* Use **clear, specific commit messages**
* Push to GitHub via GitHub Desktop

***

### ✅ Week 7 Checklist

* [ ] Added at least 2 new charts with new questions or variables
* [ ] Used `groupby()` for categorical comparisons
* [ ] Created a trend/timeline chart
* [ ] Documented emerging insights
* [ ] Reviewed and adjusted the original plan if needed
* [ ] Committed and pushed all code and visuals to GitHub
