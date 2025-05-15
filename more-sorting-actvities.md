# More Sorting Actvities

Task 5: Aggregating with `groupby()`

```python
# Average height per sport
avg_height = df.groupby('Sport')['Height'].mean().sort_values(ascending=False)
print(avg_height.head())

# Median age by year
median_age_by_year = df.groupby('Year')['Age'].median()
print(median_age_by_year.tail())
```

**Challenge**:

* Create a new group that shows **average weight** by **Sex and Sport**

***

Task 6: Exporting a Subset

```python
# Filter gymnasts and save to new CSV
gymnasts = df[df['Sport'] == 'Gymnastics']
gymnasts.to_csv('gymnastics_athletes.csv', index=False)
```

Try exporting:

* All **athletes under 18**
* All **athletes who won a gold medal**

***

### 📚 Reflection Journal

In your GitBook or project notebook, answer:

1. What was the **easiest filtering task** and why?
2. What was the **most difficult grouping or sorting task**?
3. What trends surprised you in the Olympic data?
4. What kinds of **real-world questions** could this kind of analysis help answer?

***

### GitHub Workflow

After **each task**, do the following:

* ✅ Save `main.py`
* ✅ Open GitHub Desktop
* ✅ Write a meaningful commit message (e.g. "Grouped medal counts by team")
* ✅ Click **Commit to main** and **Push origin**

***

### ✅ Week 3 Checklist

* [ ] Completed and committed 6 data analysis tasks
* [ ] Practised filtering, sorting, and grouping
* [ ] Saved a filtered CSV subset
* [ ] Reflected in journal
* [ ] Pushed all work to GitHub
