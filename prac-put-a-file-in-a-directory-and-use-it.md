---
icon: user-robot
---

# Prac - Put a file in a Directory and use it

## 📁 Working with File Paths in Python (No Libraries)

This guide shows you how to work with file and folder paths using **plain Python**

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

### 📦 Project Structure Example

Assume your folder looks like this:

```
MyProject/
│
├── main.py
└── data/
    └── students.csv
```

***

### 🔹 Step 1: Use a Simple String as the File Path

```python
# This is a relative path
file_path = "data/students.csv"
```

> ✅ Tip: Always use forward slashes `/` — even on Windows.

***

### 🔹 Step 2: Open and Read the File (Basic Way)

```python
file = open("data/students.csv", "r", encoding="utf-8")

contents = file.read()

print(contents)

file.close()
```

***

### 🔹 Step 3: Open the File Using `with` (Better)

```python
with open("data/students.csv", "r", encoding="utf-8") as file:
    contents = file.read()
    print(contents)
```

***

### 🔹 Step 4: Build the Path with Strings

This is the best way to manage paths to files without using an external library widget. The benefit here is you can rename the variabesl later if you need to and not have to change them in the script - where you might have several **hard coded paths** which would need to be replaced.

```python
folder = "data"
filename = "students.csv"

file_path = folder + "/" + filename

with open(file_path, "r", encoding="utf-8") as file:
    print(file.read())
```

***

<figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption><p>This example has a directory called data and that has a sub directory called sub_directory</p></figcaption></figure>

{% hint style="info" %}
The best method is to keep it simple at this stage - make a variable called `folder` and one called `filename` then use that to build a variable called `filepath`. Less hard coding (see step 4)
{% endhint %}

### Notes and Best Practices

* Only use this method if your files are in predictable, simple folder structures.
* Don’t use backslashes (`\`) in paths. They are used for escape characters (like , , etc.).
* Always close the file, or use the `with` statement to do it automatically.

***

Now you're ready to read files from folders like a pro — no libraries required!
