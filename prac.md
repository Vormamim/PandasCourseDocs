---
icon: user-robot
---

# Prac

## 📁 Working with File Paths in Python (No Libraries)

This guide shows you how to work with file and folder paths using **plain Python**

***

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

```python
folder = "data"
filename = "students.csv"

file_path = folder + "/" + filename

with open(file_path, "r", encoding="utf-8") as file:
    print(file.read())
```

***

### ⚠️ Notes and Best Practices

* Only use this method if your files are in predictable, simple folder structures.
* Don’t use backslashes (`\`) in paths. They are used for escape characters (like , , etc.).
* Always close the file, or use the `with` statement to do it automatically.

***

Now you're ready to read files from folders like a pro — no libraries required!
