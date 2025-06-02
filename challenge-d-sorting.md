---
hidden: true
icon: filters
---

# Challenge D - Sorting

## Pandas Challenge: Analysing Student Grades

This challenge will help you practice filtering, sorting, and grouping data using Pandas.\
You will work with a CSV file called `grades.csv` containing student grades.

### Example Data

Your `grades.csv` file should look like this:

```
Name,Subject,Score,Year
Alice,Math,85,2024
Bob,Math,78,2024
Alice,English,92,2024
Bob,English,88,2024
Charlie,Math,90,2024
Charlie,English,85,2024
```

### Use Mockaroo to make a fake data set

{% embed url="https://www.mockaroo.com/" %}

First of all, generate a simple data set as a sample for the app to work out what you want.

Just copy the code above to into the box called "derive from example"

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Adjust your file using the intererace to get a data set you want, then hit generate.

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Now you will have a sheet to work with that might look like this

<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

***

### Part 1: Load the Data

* Import pandas and load the `grades.csv` file into a DataFrame.
* Print the first 5 rows.

***

### Part 2: Filtering

* Filter the DataFrame to show only the rows where the `Score` is greater than 85.
* Print the result.

***

### Part 3: Sorting

* Sort the DataFrame by `Score` in descending order.
* Print the top 3 rows.

***

### Part 4: Grouping and Aggregation

* Group the data by `Name` and calculate the average score for each student.
* Print the result.

***

### Part 5: Challenge Extension

* Which student has the highest average score? Print their name and average score.

***

**Tip:**\
You may want to use these Pandas methods:

* `.read_csv()`
* `.loc[]`
* `.sort_values()`
* `.groupby()`
* `.mean()`

## Hints

```
Paths
'dummy_data.csv' → same folder as your script
'data/dummy_data.csv' → in a subfolder called data
'../dummy_data.csv' → in the parent folder of your scrip
```
