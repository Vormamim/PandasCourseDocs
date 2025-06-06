---
icon: notebook
---

# Referencing Parent and Sub-Directories in VS Code

### <mark style="background-color:red;">The page is a PRACTICAL which requires YOU to understand the relationship between your script and directories where data is stored.</mark>&#x20;

### <mark style="background-color:red;">You don't need to hand this in.</mark>

You might need to mess around and experiment with folders and file structures until it 'clicks'. Make a new file called `directory_manager.py` and then work through the examples to understanding **paths.**

Paths and directories are like the map and addresses of a computer’s file system. A **directory** is like a folder where files are stored. The **path** is the specific address that tells the computer where a file or directory is located. There are two types of paths: **absolute paths** start from the root of the file system and show the full location, while **relative paths** are based on the current directory, showing a location relative to where you currently are. Understanding paths helps you navigate and manage your files effectively.

You will be using RELATIVE PATHS for your project as everything is 'relative' to the workspace (master repository) that you created for this unit of work. Everything else is either in it at the **root level** or a folder - which is called **directory.**

### Understanding Root Files

In a file system, the **root directory** is the top-most directory, and it's the starting point for the hierarchy of files and directories. Files located in the root directory are often referred to as **root files**. In your project folder structure, these are the files that reside directly within the main workspace directory without being nested in sub-folders. Root files are typically accessible from any sub-directory using relative paths, and they play a crucial role in organising key files that need to be easily accessible, such as configuration files or primary scripts. In the context of the example given, `outtie.csv` located directly under `MyProject/` is an example of a root file.&#x20;

We're going to use the folder structure below to work our way through the idea of parent-child relationships for paths.

***

### 📂 Folder Structure

Assume this is your folder structure inside **VS Code**:

```
MyRepo/ - #Im the workspace parent dirctory
├── outtie.csv #I'm a file the workspace parent directory
├── Week_3/ #Im a sub-directory. I'm a child of the parent directory
│   └── innie.csv #I'm a file who lives in the workspace/sub-directors
│   └── script.py #My path is Week_3/script.py
```

You are writing `script.py` inside the **Week 3** folder and want to:

1. Read `innie.csv` (same folder)
2. Read `outtie.csv` (parent folder)

```python
import pandas as pd

# Demo: Reading CSV files using different relative paths

# 1. Reading a file in the same directory as this script
# df_same_dir = pd.read_csv('somefile.csv')

# 2. Reading a file in a sub-directory (e.g., Week_3/innie.csv)
df_innie = pd.read_csv('Week_3/innie.csv')
print("Reading from sub-directory (Week_3/innie.csv):")
print(df_innie.head())

# 3. Reading a file in the parent directory (e.g., ../outtie.csv)
df_outtie = pd.read_csv('../outtie.csv')
print("\nReading from parent directory (../outtie.csv):")
print(df_outtie.head())
```

### Task 1 : Accessing a File in the Same Directory

To read `innie.csv` from the same folder (`Week 3`):

<mark style="background-color:orange;">**This is the most common structure you will be making in this course. file and script in the same directory.**</mark>

```python
import pandas as pd

df_in = pd.read_csv("innie.csv")
print(df_in.head())
```

**Tip**: No need to specify any folder path — just the filename.

***

### Task 2: Accessing a File in the Parent Directory

To access `outtie.csv` from inside the `Week 3` folder:

```python
import pandas as pd

df_out = pd.read_csv("../outtie.csv")
print(df_out.head())
```

**Tip**:

* `..` means "go up one folder" (i.e., to the parent directory)
* You can chain `../` if needed to go up more levels

***

### Summary of Path Types

| Type           | Example             | Description                               |
| -------------- | ------------------- | ----------------------------------------- |
| Same directory | `"innie.csv"`       | File in the same folder                   |
| Parent folder  | `"../outtie.csv"`   | File in the folder one level up           |
| Sub-folder     | `"folder/file.csv"` | File in a sub-directory of current folder |

### Absolute vs Relative Paths

* **Relative path** (preferred): `"../outtie.csv"` → Portable and works on different machines
* <mark style="background-color:red;">**Absolute path**</mark><mark style="background-color:red;">:</mark> <mark style="background-color:red;"></mark><mark style="background-color:red;">`"/Users/yourname/Documents/MyProject/outtie.csv"`</mark> <mark style="background-color:red;"></mark><mark style="background-color:red;">→ Not portable, only works on your machine.</mark> <mark style="background-color:red;"></mark><mark style="background-color:red;">**Avoid using Absolute paths!**</mark>
