# Internal, Export and Load

This code uses a **dictionary** to create a data. It then shows you how to save data and then load it again. All good practice for the Karate Kid right?

A **dictionary** in Python is a way to store data in pairs: each piece of data has a **key** (like a label or a name) and a **value** (the information).\
It looks like this:

my\_dict = {'Name': 'Alice', 'Age': 25}

* `'Name'` is a key, and `'Alice'` is its value.
* `'Age'` is a key, and `25` is its value.

You can use the key to quickly find the value, just like looking up a word in a real dictionary!

<mark style="background-color:yellow;">Not sure what a Dictionary is or can do? -</mark> [<mark style="background-color:yellow;">https://www.w3schools.com/python/python\_dictionaries.asp</mark>](https://www.w3schools.com/python/python_dictionaries.asp)

```python
import pandas as pd

def main():
    # Create a DataFrame with some sample data
    data = {
        'Name': ['Alice', 'Bob', 'Charlie'],
        'Age': [25, 30, 35],
        'City': ['New York', 'Los Angeles', 'Chicago']
    }
    
    df = pd.DataFrame(data)
    
    # Display the DataFrame
    print("DataFrame:")
    print(df)

    # Save the DataFrame to a CSV file
    df.to_csv('sample_data.csv', index=False)
    print("\nDataFrame saved to 'sample_data.csv'.")

    # Read the DataFrame from the CSV file
    df_loaded = pd.read_csv('sample_data.csv')

    print("\nDataFrame loaded from 'sample_data.csv':")

    # Display the loaded DataFrame
    print(df_loaded)
```

Why do you think these three operations are key to working with data and information?
