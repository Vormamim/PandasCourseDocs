# Add a Live Matplotlib Chart to Your Dashboard



#### GOAL:

You will learn how to:

* Create a chart using Matplotlib
* Display it **inside your CustomTkinter window**
* Let the user refresh the chart interactively

***

### ✅ Step-by-Step Instructions

#### 🧰 STEP 1: Import These Extra Libraries

At the top of your script, **add these two lines**:

```python
from matplotlib.backends.backend_tkagg import FigureCanvasTkAgg
import matplotlib.pyplot as plt
```

✅ Make sure you already have `matplotlib` installed: Check first using `pip list`

```
pip list
```

```bash

pip install matplotlib
```

***

#### STEP 2: Create a Function to Draw a Chart

Add this below your existing functions:

```python
def draw_chart():
    # Create a simple bar chart of average calories by activity
    grouped = df.groupby('Activity')['Calories'].mean().sort_values(ascending=False).head(5)

    # Clear previous figure if it exists
    for widget in chart_frame.winfo_children():
        widget.destroy()

    fig, ax = plt.subplots(figsize=(5, 3))
    grouped.plot(kind='bar', ax=ax, color='orange')
    ax.set_title("Top 5 Activities by Calories Burned")
    ax.set_ylabel("Calories")
    ax.set_xlabel("Activity")
    plt.tight_layout()

    canvas = FigureCanvasTkAgg(fig, master=chart_frame)
    canvas.draw()
    canvas.get_tk_widget().pack()
```

***

#### STEP 3: Add a Chart Frame

**Near your existing `frame`**, insert this:

```python
chart_frame = ctk.CTkFrame(master=app)
chart_frame.pack(pady=10, padx=20, fill="both", expand=True)
```

This is where your chart will appear.

***

#### STEP 4: Add a Button to Draw or Refresh Chart

Below your other buttons, add:

```python
pythonCopyEditchart_button = ctk.CTkButton(master=frame, text="Show Chart", command=draw_chart)
chart_button.pack(pady=10)
```

✅ When you click the button, the chart will appear or refresh inside the dashboard.

***

#### Run the App

If everything is working:

* The chart will show when the button is pressed
* You can edit the chart function later to display other comparisons (e.g. steps, sleep, etc.)

***

### ✅ Week 15 Checklist

* [ ] Imported `FigureCanvasTkAgg` and `matplotlib.pyplot`
* [ ] Chart appears inside your dashboard in a new frame
* [ ] Button triggers the chart function
* [ ] No grid or advanced layout used — only `.pack()`
* [ ] Pushed final dashboard version to GitHub

***

> 🏁 You’ve now created a fully working Python data dashboard using Pandas, Matplotlib, and CustomTkinter. You can read, filter, analyse, and visualise real data — in an app you designed yourself!
