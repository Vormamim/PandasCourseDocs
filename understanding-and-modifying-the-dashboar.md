# Understanding & Modifying the Dashboar

ou will learn how to:

* Read and understand a working Tkinter dashboard
* Change labels, fonts, and colours
* Add new labels and a simple button

***



#### 🗂️ STEP 1: Start with the Template

Open your file: `health_dashboard.py`

At the top, make sure you have:

```python
import customtkinter as ctk
import pandas as pd

df = pd.read_csv("health_activity_data.csv")
df.fillna(0, inplace=True)
```

***

#### 🖥️ STEP 2: Create the Window

Use this setup to create the window and frame:

```python
ctk.set_appearance_mode("dark")
ctk.set_default_color_theme("blue")

app = ctk.CTk()
app.geometry("500x400")
app.title("Health Tracker Dashboard")

frame = ctk.CTkFrame(master=app)
frame.pack(pady=20, padx=20, fill="both", expand=True)
```

***

#### 🧮 STEP 3: Show Three Statistics

Below the frame, add this code:

```python
avg_steps = int(df["Steps"].mean())
avg_calories = int(df["Calories"].mean())
avg_sleep = round(df["SleepHours"].mean(), 1)

steps_label = ctk.CTkLabel(frame, text=f"🦶 Steps: {avg_steps}", font=("Arial", 18))
steps_label.pack(pady=10)

cal_label = ctk.CTkLabel(frame, text=f"🔥 Calories: {avg_calories}", font=("Arial", 18))
cal_label.pack(pady=10)

sleep_label = ctk.CTkLabel(frame, text=f"😴 Sleep: {avg_sleep} hrs", font=("Arial", 18))
sleep_label.pack(pady=10)
```

✅ **Run your code now** — you should see three labels in the window.

***

#### 🖱️ STEP 4: Add a Refresh Button

Now add this underneath the labels:

```python
def refresh():
    new_avg = round(df["SleepHours"].mean(), 2)
    sleep_label.configure(text=f"😴 Sleep: {new_avg} hrs")

button = ctk.CTkButton(frame, text="Refresh Sleep", command=refresh)
button.pack(pady=15)
```

✅ **Try it**: Change one number in the dataset to see the button update the result when pressed.

***

#### 🎨 STEP 5: Change Style (Optional)

Change:

* Font: try `"Courier New"` or `"Comic Sans MS"`
* Colour theme: change `"blue"` to `"green"` at the top

You can also change this line:

```python
app.geometry("700x500")
```

...to make the window larger!

***

### ✅ GUI Checklist

* [ ] Opened and ran the base dashboard
* [ ] Modified text on at least one label
* [ ] Added a refresh button
* [ ] Changed font, size, or colour
* [ ] Pushed your updated file to GitHub
