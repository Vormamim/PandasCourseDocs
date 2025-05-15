# Data Visualisation – Bringing Data to Life



### Learning Objectives

You will:

* Use Pandas and Matplotlib to create visualisations
* Create bar charts, line graphs, histograms, and pie charts
* Apply visualisation principles to tell data stories
* Reflect on visual clarity, labels, and insights

***

### Estimated Time: 3 Hours

Complete the **six scaffolded tasks**, and commit your code and images after each step.

***

### 📂 Prerequisites

* You've cleaned your dataset (`athlete_events_cleaned.csv`)
* Matplotlib is installed:

```bash
pip install matplotlib
```

Task 1: Import Matplotlib

In your `main.py`, import the following:

```python
import matplotlib.pyplot as plt
```

Then re-load your cleaned data:

```python
import pandas as pd

df = pd.read_csv("athlete_events_cleaned.csv")
```

***

Task 2: Bar Chart – Top 10 Sports by Participation

```python
sport_counts = df['Sport'].value_counts().head(10)

sport_counts.plot(kind='bar', title='Top 10 Sports by Athlete Count')
plt.xlabel('Sport')
plt.ylabel('Number of Athletes')
plt.xticks(rotation=45)
plt.tight_layout()
plt.savefig("top_10_sports.png")
plt.show()
```

Check:

* Are labels readable?
* Does the chart title clearly explain what’s shown?

***

Task 3: Line Graph – Median Age Over Time

```python
median_age = df.groupby('Year')['Age'].median()

median_age.plot(kind='line', title='Median Athlete Age Over Time')
plt.xlabel('Olympic Year')
plt.ylabel('Median Age')
plt.grid(True)
plt.tight_layout()
plt.savefig("median_age_line.png")
plt.show()
```

Reflect:

* Is there a trend over time?
* Does this graph suggest changes in athlete demographics?

***

Task 4: Histogram – Distribution of Athlete Weights

```python
df['Weight'].plot(kind='hist', bins=30, title='Distribution of Athlete Weights')
plt.xlabel('Weight (kg)')
plt.ylabel('Frequency')
plt.tight_layout()
plt.savefig("weight_distribution.png")
plt.show()
```

Try:

* Change `bins=30` to `bins=10`. What changes?
* Describe the **shape** of the data: is it normal, skewed, or unusual?

***

Task 5: Pie Chart – Medals by Type

```python
medal_counts = df[df['Medal'] != 'None']['Medal'].value_counts()

medal_counts.plot(kind='pie', autopct='%1.1f%%', title='Distribution of Medal Types')
plt.ylabel('')  # Removes default y-axis label
plt.tight_layout()
plt.savefig("medal_pie_chart.png")
plt.show()
```

📝 What percentage of medals are **gold**, silver, and bronze?

***

Task 6: Create Your Own Chart

Design a chart to answer a question you find interesting. Ideas:

* Average height by sport
* Top 5 countries in a specific year
* Medal breakdown by gender

Include:

* Clear title
* Axis labels
* Save as PNG (e.g. `"my_custom_chart.png"`)

***

### Reflection Journal

Answer in your journal

1. Which chart was **easiest** to understand? Why?
2. Which chart was **hardest to interpret**? Why?
3. How can visualising data help you make better decisions?

***

### REMINDER: Save, Commit, Push

After **each visualisation**:

* Save your Python file and image(s)
* Open GitHub Desktop
* Add a clear commit message (e.g. “Added line chart of median age”)
* Click **Commit to main**, then **Push origin**

***

### ✅ Week 5 Checklist

* [ ] Created a bar chart for top 10 sports
* [ ] Created a line graph of median age
* [ ] Created a histogram for athlete weight
* [ ] Created a pie chart of medal types
* [ ] Designed a custom chart
* [ ] Reflected and committed all work to GitHub
