# Explore a GUI data app

<mark style="background-color:blue;">There was no Week 9</mark>

<mark style="background-color:blue;">You will need to install customTKinter in the terminal</mark>

`pip install customTKinter`

```python
import customtkinter as ctk
import pandas as pd

# Setup
ctk.set_appearance_mode("dark")
ctk.set_default_color_theme("blue")

# Load dataset
df = pd.read_csv("health_activity_data.csv")

# Optional: fill missing values
df.fillna(0, inplace=True)

# Window
app = ctk.CTk()
app.title("Health Data Dashboard")
app.geometry("600x400")

# Frame
frame = ctk.CTkFrame(master=app)
frame.pack(padx=20, pady=20, fill="both", expand=True)

# Sample calculations
avg_steps = int(df["Steps"].mean())
avg_calories = int(df["Calories"].mean())
avg_sleep = round(df["SleepHours"].mean(), 1)

# Labels
steps_label = ctk.CTkLabel(master=frame, text=f"🦶 Avg Steps: {avg_steps}", font=("Arial", 18))
steps_label.pack(pady=10)

cal_label = ctk.CTkLabel(master=frame, text=f"🔥 Avg Calories: {avg_calories}", font=("Arial", 18))
cal_label.pack(pady=10)

sleep_label = ctk.CTkLabel(master=frame, text=f"😴 Avg Sleep: {avg_sleep} hrs", font=("Arial", 18))
sleep_label.pack(pady=10)

# Optional dropdown by user (if 'User_ID' exists)
if 'User_ID' in df.columns:
    users = df['User_ID'].unique().astype(str)
    selected_user = ctk.StringVar(value=users[0])

    def user_selected(choice):
        user_data = df[df['User_ID'] == int(choice)]
        steps = int(user_data["Steps"].mean())
        calories = int(user_data["Calories"].mean())
        sleep = round(user_data["SleepHours"].mean(), 1)

        steps_label.configure(text=f"🦶 Avg Steps: {steps}")
        cal_label.configure(text=f"🔥 Avg Calories: {calories}")
        sleep_label.configure(text=f"😴 Avg Sleep: {sleep} hrs")

    dropdown = ctk.CTkOptionMenu(master=frame, values=list(users), command=user_selected)
    dropdown.pack(pady=20)
    dropdown.set(users[0])

# Run the app
app.mainloop()

```
