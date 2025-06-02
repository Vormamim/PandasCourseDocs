# Referencing Parent and Sub-Directories in VS Code

Learn how to correctly reference files stored in **parent** and **sub-directories** using relative paths in VS Code. You’ll use a real-world folder structure to read `.csv` files from different locations.

***

### 📂 Folder Structure

Assume this is your folder structure inside **VS Code**:

```
MyProject/
├── outtie.csv
├── Week_3/
│   └── innie.csv
│   └── script.py
```

You are writing `script.py` inside the **Week 3** folder and want to:

1. Read `innie.csv` (same folder)
2. Read `outtie.csv` (parent folder)

***

### ✅ Task 1: Accessing a File in the Same Directory

To read `innie.csv` from the same folder (`Week 3`):

```python
import pandas as pd

df_in = pd.read_csv("innie.csv")
print(df_in.head())
```

**Tip**: No need to specify any folder path — just the filename.

***

### ✅ Task 2: Accessing a File in the Parent Directory

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

***

### 🛠️ Bonus: Absolute vs Relative Paths

* **Relative path** (preferred): `"../outtie.csv"` → Portable and works on different machines
* **Absolute path**: `"/Users/yourname/Documents/MyProject/outtie.csv"` → Not portable, only works on your machine

***

### Practical - Make sure you can do this

Add a new folder called `Data` inside `MyProject`, move `innie.csv` there, and update your script to read it using a relative path.

✅ Path should look like:

```
CMyProject/
├── outtie.csv
├── Week_2/
│   └── innie.csv
├── Week_3/
│   └── script.py
```

✍️ Try to reference `innie.csv` now from `Week 3/script.py`:

```python
df_in = pd.read_csv("../Week_2/innie.csv")
```
