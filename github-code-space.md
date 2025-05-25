---
icon: code-branch
---

# GitHub Code Space

Create a code-space inside your repository. This is from the GREEN code button. Click the box that says 'add a README.md' file.

<figure><img src=".gitbook/assets/Screenshot 2025-05-26 at 8.32.44 am.png" alt=""><figcaption></figcaption></figure>

Choose Code Spaces

<figure><img src=".gitbook/assets/Screenshot 2025-05-26 at 8.38.06 am.png" alt=""><figcaption></figcaption></figure>

Create a Code Space

<figure><img src=".gitbook/assets/Screenshot 2025-05-26 at 8.38.39 am.png" alt=""><figcaption></figcaption></figure>

A Code Space is the same as running VS Code on your machine, but with less functionality overall. When you open your codespace, you will see the normal looking IDE.

Create a new file called **main.py** and a new file for Python will be created.

At this point, The codespace will detect python and will want to install Python extensions. Y**ou are familiar with extensions. This is no different to previous projects.**

<figure><img src=".gitbook/assets/Screenshot 2025-05-26 at 8.40.33 am.png" alt=""><figcaption></figcaption></figure>

You will need a README file which can act as a logbook (this is not the same as the dairy) Use the read me to 'log' things you have coded only

<figure><img src=".gitbook/assets/Screenshot 2025-05-26 at 8.46.23 am.png" alt=""><figcaption></figcaption></figure>

Create a simple Pandas Data Structure

### Create a simple Pandas Data Frame

A DataFrame is a 2-dimensional, size-mutable, and potentially <mark style="background-color:orange;">heterogeneous</mark> tabular data structure with labeled axes (rows and columns) provided by the Pandas library in Python. It is similar to a spreadsheet or SQL table, efficiently handling large datasets and allowing various operations such as filtering, grouping, and merging data.

**Heterogeneous** refers to the composition of elements that are diverse in character or content. In the context of data structures like a Pandas DataFrame, it means that the data can contain different types of data in each column, such as integers, floats, strings, or other objects, providing flexibility in handling various forms of data within a single structure.

Use this code. Paste into your **main.py** file and **run** the code

```python
import pandas as pd

# Create a simple list
data = [1, 2, 3, 4, 5]

# Create a DataFrame from the list
df = pd.DataFrame(data, columns=['Numbers'])

print(df)
```

**What did I just do?**

Alright! Imagine you have a list of your five  numbers: 1, 2, 3, 4, and 5. You want to put these numbers in a table with the title "Numbers" on top so they become organised.

Here's how we do that using something called "Pandas," which is like a helper that lets us make tables easily:

1. We start by telling our computer we want to use Pandas by writing `import pandas as pd`. It's like saying, "We want the Pandas helper here!"

```
   Numbers
0        1
1        2
2        3
3        4
4        5
```

The output will look like this. The column on the left is the INDEX (position) of the data in the data fame.

### Pandas has tool to help wrangle data

Add this to the code and run again.

Why do you think def.iterrows() does? what does the 'dot' signify to Pandas?

```python
# create a loop and run through the data frame
for index, row in df.iterrows():
    print(f"Index: {index}, Value: {row['Numbers']}")
```

