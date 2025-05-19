# Activities 2

### Activity 1: Describe the Dataset

Answer in your GitBook log or project journal:

1. How many **columns** are in the dataset?
2. Name 3 of them and explain what they represent.
3. What do the first 5 rows show?

***

### Activity 2: Explore Columns

Add this code to your script:

```python
print(df['Sport'].value_counts().head())
print(df['Sex'].value_counts())
```

Then answer:

* What are the **top 5 sports**?
* How many male vs female athletes?

***

### Activity 3: Quick Stats with `describe()`

Add this line to your script:

```python
print(df.describe())
```

Then:

* What’s the **average age**?
* What’s the **oldest** and **youngest** athlete?
* Are there any columns with **missing or strange values**?

***

### Extension: Explore Country Codes

Try this:

```python
print(df['NOC'].nunique())
print(df['NOC'].unique())
```

Research what three of the lesser-known codes stand for, e.g. `URS`, `GDR`, `FRG`.

***

### **REMEMBER: Pull Before You Push (at school/home)**

If you continue this project on another device or later at home:

1. **Open GitHub Desktop**
2. Click **Pull origin** to get the latest version
3. Then open and continue your code

Always **pull before working**, and **push when you’re done**!

***

### Reflection

Write a short reflection in your GitBook journal:

* What’s one thing you learned about the Olympics dataset?
* What did you find challenging in setting up or running Pandas?
* What’s something you'd like to analyse next?
