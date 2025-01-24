import tkinter as tk
from tkinter import messagebox

def submit_form():
    name = entry_name.get()
    email = entry_email.get()
    password = entry_password.get()
    age = entry_age.get()

    # Simple validation
    if not name or not email or not password or not age:
        messagebox.showerror("Input Error", "Please fill out all fields")
        return

    # Normally, you would save the data to a database or file, but here we just display a success message
    messagebox.showinfo("Registration Success", f"Welcome, {name}! You've successfully registered.")

# Create the main window
root = tk.Tk()
root.title("Registration Form")

# Create and place labels and entry widgets for each form field
label_name = tk.Label(root, text="Name:")
label_name.grid(row=0, column=0, padx=10, pady=5)
entry_name = tk.Entry(root)
entry_name.grid(row=0, column=1, padx=10, pady=5)

label_email = tk.Label(root, text="Email:")
label_email.grid(row=1, column=0, padx=10, pady=5)
entry_email = tk.Entry(root)
entry_email.grid(row=1, column=1, padx=10, pady=5)

label_password = tk.Label(root, text="Password:")
label_password.grid(row=2, column=0, padx=10, pady=5)
entry_password = tk.Entry(root, show="*")  # Hides password input
entry_password.grid(row=2, column=1, padx=10, pady=5)

label_age = tk.Label(root, text="Age:")
label_age.grid(row=3, column=0, padx=10, pady=5)
entry_age = tk.Entry(root)
entry_age.grid(row=3, column=1, padx=10, pady=5)

# Create a submit button
submit_button = tk.Button(root, text="Submit", command=submit_form)
submit_button.grid(row=4, column=0, columnspan=2, pady=10)

# Run the application
root.mainloop()
