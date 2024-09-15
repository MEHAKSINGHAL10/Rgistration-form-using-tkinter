import tkinter as tk
from tkinter import messagebox
import re

# Function to handle form submission
def submit_form():
    first_name = first_name_entry.get()
    last_name = last_name_entry.get()
    email = email_entry.get()
    age = student_id_entry.get()
    password = password_entry.get()
    address = address_entry.get()
    gender = gender_var.get()

    if first_name and last_name and email and age and password and address and gender != "Please Select":
        password_error = validate_password(password)
        if password_error:
            messagebox.showerror("Error", password_error)
        else:
            print(f"Student Name: {first_name} {last_name}")
            print(f"Gender: {gender}")
            print(f"Email: {email}")
            print(f"Student ID: {age}")
            print(f"Address: {address}")
            messagebox.showinfo("Form Submission", "Form submitted successfully!")
    else:
        messagebox.showerror("Error", "Please fill in all fields.")

# Function to validate password
def validate_password(password):
    if len(password) < 8 or len(password) > 15:
        return "Password must be between 8 and 15 characters long."
    if not re.search(r'[A-Z]', password):
        return "Password must contain at least one uppercase letter."
    if not re.search(r'[a-z]', password):
        return "Password must contain at least one lowercase letter."
    if not re.search(r'[0-9]', password):
        return "Password must contain at least one number."
    if not re.search(r'[!@#$%^&*(),.?\":{}|<>]', password):
        return "Password must contain at least one special character."
    return None

# Main window
root = tk.Tk()
root.title("Professional Registration Form")
root.geometry("700x800")
root.configure(bg="#F0F4F7")  # Light grayish-blue background for a modern look

# Form Title
title_label = tk.Label(root, text="Next24Tech", font=("Arial", 28, "bold"), bg="#F0F4F7", fg="#333333")
title_label.pack(pady=20)

subtitle_label = tk.Label(root, text="Fill out the form carefully for registration", font=("Arial", 14), bg="#F0F4F7", fg="#666666")
subtitle_label.pack(pady=10)

# Frame for form fields
form_frame = tk.Frame(root, bg="#ffffff", padx=30, pady=30, relief="groove", bd=3)
form_frame.pack(pady=20, fill="both", expand=True)

# Field spacing
field_spacing = {"padx": 10, "pady": 10}

# Student Name Fields (First Name, Last Name)
first_name_label = tk.Label(form_frame, text="First Name", font=("Arial", 14, "bold"), bg="#ffffff", fg="#333333")
first_name_label.grid(row=0, column=0, sticky="w", **field_spacing)
first_name_entry = tk.Entry(form_frame, width=35, font=("Arial", 14), bd=3, relief="solid")
first_name_entry.grid(row=0, column=1, **field_spacing)

last_name_label = tk.Label(form_frame, text="Last Name", font=("Arial", 14, "bold"), bg="#ffffff", fg="#333333")
last_name_label.grid(row=0, column=2, sticky="w", **field_spacing)
last_name_entry = tk.Entry(form_frame, width=35, font=("Arial", 14), bd=3, relief="solid")
last_name_entry.grid(row=0, column=3, **field_spacing)

# Gender (Radio Buttons)
gender_label = tk.Label(form_frame, text="Gender", font=("Arial", 14, "bold"), bg="#ffffff", fg="#333333")
gender_label.grid(row=1, column=0, sticky="w", **field_spacing)

gender_var = tk.StringVar(value="Please Select")
tk.Radiobutton(form_frame, text="Male", variable=gender_var, value="Male", font=("Arial", 14), bg="#ffffff", fg="#333333").grid(row=1, column=1, sticky="w", padx=5)
tk.Radiobutton(form_frame, text="Female", variable=gender_var, value="Female", font=("Arial", 14), bg="#ffffff", fg="#333333").grid(row=1, column=2, sticky="w", padx=5)
tk.Radiobutton(form_frame, text="Other", variable=gender_var, value="Other", font=("Arial", 14), bg="#ffffff", fg="#333333").grid(row=1, column=3, sticky="w", padx=5)

# Student Email
email_label = tk.Label(form_frame, text="E-mail", font=("Arial", 14, "bold"), bg="#ffffff", fg="#333333")
email_label.grid(row=2, column=0, sticky="w", **field_spacing)
email_entry = tk.Entry(form_frame, width=35, font=("Arial", 14), bd=3, relief="solid")
email_entry.grid(row=2, column=1, **field_spacing)

# Student ID
student_id_label = tk.Label(form_frame, text="Age", font=("Arial", 14, "bold"), bg="#ffffff", fg="#333333")
student_id_label.grid(row=3, column=0, sticky="w", **field_spacing)
student_id_entry = tk.Entry(form_frame, width=35, font=("Arial", 14), bd=3, relief="solid")
student_id_entry.grid(row=3, column=1, **field_spacing)

# Address Field
address_label = tk.Label(form_frame, text="Address", font=("Arial", 14, "bold"), bg="#ffffff", fg="#333333")
address_label.grid(row=4, column=0, sticky="w", **field_spacing)
address_entry = tk.Entry(form_frame, width=35, font=("Arial", 14), bd=3, relief="solid")
address_entry.grid(row=4, column=1, **field_spacing)

# Password Field
password_label = tk.Label(form_frame, text="Password", font=("Arial", 14, "bold"), bg="#ffffff", fg="#333333")
password_label.grid(row=5, column=0, sticky="w", **field_spacing)
password_entry = tk.Entry(form_frame, width=35, font=("Arial", 14), bd=3, relief="solid", show="*")
password_entry.grid(row=5, column=1, **field_spacing)

# Submit Button
submit_button = tk.Button(form_frame, text="Submit", command=submit_form, font=("Arial", 16, "bold"), 
                          bg="#4CAF50", fg="#ffffff", padx=20, pady=10, width=12, cursor="hand2")
submit_button.grid(row=6, column=1, columnspan=2, pady=30)  # Centered the button

# Footer
footer_frame = tk.Frame(root, bg="#2e3d4f", padx=20, pady=10)
footer_frame.pack(side="bottom", fill="x")

footer_label = tk.Label(footer_frame, text="Copyright 2023 Next24Tech. All rights reserved.\nAddress: Goregaon, Gondia, 441801 India \nPhone no: +91 9112327362", 
                        font=("Arial", 12), fg="#ffffff", bg="#2e3d4f", anchor="w")
footer_label.pack()

# Start the main loop
root.mainloop()
