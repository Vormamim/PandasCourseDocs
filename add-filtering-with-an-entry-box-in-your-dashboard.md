# Add Filtering with an Entry Box in Your Dashboard

#### GOAL:

You will learn how to:

* Add a text input (entry box)
* Let the user type in a number (e.g. minimum steps)
* Use a button to **filter** the dataset and display a result

***

### ✅ Step-by-Step Instructions

#### STEP 1: Continue from Your Last File

Reopen your dashboard file `health_dashboard.py`.

You should already have:

* Imported Pandas and CustomTkinter
* Loaded `health_activity_data.csv`
* Created a window, frame, and some labels

✅ Confirm that your file runs before continuing.

***

#### 🔤 STEP 2: Add an Entry Box

Add this code **below your existing labels**, but **above your mainloop**:

```python
# Entry for minimum steps
entry_label = ctk.CTkLabel(frame, text="Enter minimum number of steps:", font=("Arial", 14))
entry_label.pack(pady=(20, 5))

steps_entry = ctk.CTkEntry(frame, placeholder_text="e.g. 5000")
steps_entry.pack(pady=5)
```

✅ Run your code: you should now see a label and an entry box appear.

***

#### 🖱️ STEP 3: Add a Filter Button

Now add a button to use the value from the entry box:

```python
def filter_steps():
    try:
        min_steps = int(steps_entry.get())
        filtered = df[df["Steps"] >= min_steps]
        count = len(filtered)
        steps_label.configure(text=f"🦶 Users with ≥ {min_steps} steps: {count}")
    except ValueError:
        steps_label.configure(text="❗ Please enter a valid number")

filter_button = ctk.CTkButton(frame, text="Filter", command=filter_steps)
filter_button.pack(pady=10)
```

✅ Try it:

* Type a number into the entry box (like 7000)
* Click the button
* The steps label should update with how many users meet the condition

***

#### BONUS CHALLENGES (Optional)

* Duplicate this feature to filter by `Calories` or `ActiveMinutes`
* Add an **error message** if the user types letters
* Reset the label text using a **“Clear”** button

***

### ✅ Week 14 Checklist

* [ ] Entry box added successfully
* [ ] Filter button correctly updates the label
* [ ] Code works even if no value is typed (use try/except)
* [ ] CustomTkinter dashboard still looks clean and simple
* [ ] Committed all changes to GitHub with a clear message
