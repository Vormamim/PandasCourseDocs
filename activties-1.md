# Activties 1

***

### Create a practical journal markdown file

Create a Markdown file called `practical_journal.md` and save it in the synced project folder (`olympics-data-project`). This is where you will answer the various theory questions. The final commit for this will be when you've answered the reflection questions.

## Your First Pandas Script

In your synced project folder (`olympics-data-project`), open `main.py` and paste this code:

```python
import pandas as pd

# Load the dataset
df = pd.read_csv("athlete_events.csv")

# Show the first 5 rows
print(df.head())

# Show the column names
print(df.columns)
```

To run the script:

* Right-click in VS Code and choose **Run Python File in Terminal**
* Or use the ▶️ **Play button** in the top-right if it appears

#### 💾 **REMEMBER: Commit and Push!**

Once your code runs without errors:

1. Open **GitHub Desktop**
2. Write a commit message (e.g. "Loaded dataset and displayed first rows")
3. Click **Commit to main**
4. Then click **Push origin** to sync to GitHub.com
