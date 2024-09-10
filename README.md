# Ola-CyberClock
Clock for Desktop

## Python Cyber Clock ⏰

A Python desktop clock application with a Matrix-style background effect, built using the `tkinter` library. The clock updates every second and displays the current time in an easy-to-read format. The application can run in fullscreen mode to simulate a desktop background.

## Features
- 🕒 Displays the current time in `HH:MM:SS` format.
- ⏱️ Automatically updates every second.
- 🎨 Customizable fonts, colors, and window geometry.
- 🌐 Matrix-style effect with falling numbers in the background.
- 🖥️ Can run in fullscreen mode to simulate a desktop background.

## Prerequisites

Ensure you have Python 3.x installed. You can start the application by running the following command in the terminal:

```bash
sudo python3 -c "
import tkinter as tk
from time import strftime
import random

# Create the main window
root = tk.Tk()
root.title('Ola-CyberClock')

# Set fullscreen and borderless window
root.attributes('-fullscreen', True)  # Fullscreen mode
root.attributes('-topmost', True)     # Stay on top
root.config(bg='black')               # Background color

# Create a canvas for the Matrix effect
canvas = tk.Canvas(root, width=root.winfo_screenwidth(), height=root.winfo_screenheight(), bg='black', highlightthickness=0)
canvas.pack(fill='both', expand=True)

# Matrix effect settings
width, height = root.winfo_screenwidth(), root.winfo_screenheight()
columns = width // 20
drops = [0] * columns

# Function to draw Matrix effect with numbers
def draw_matrix_effect():
    canvas.delete('matrix')  # Clear previous drawings
    for i in range(columns):
        x = i * 20
        y = drops[i] * 20
        num = str(random.randint(0, 9))  # Random number
        canvas.create_text(x, y, text=num, fill='green', font=('Courier', 16), tags='matrix')
        drops[i] += 1
        if drops[i] * 20 > height or random.random() > 0.98:
            drops[i] = 0
    root.after(50, draw_matrix_effect)  # Update every 50ms

# Define the function to update the time
def update_time():
    time_string = strftime('%H:%M:%S')
    clock_label.config(text=time_string)
    clock_label.after(1000, update_time)  # Update every second

# Set up the clock label with Pt Serif font and a green theme
clock_label = tk.Label(root, font=('Pt Serif', 48), background='black', foreground='green')
clock_label.place(relx=0.5, rely=0.5, anchor='center')  # Center the clock in the window

# Start the Matrix effect and time update functions
draw_matrix_effect()  # Start drawing Matrix effect
update_time()         # Start updating the time

# Run the GUI event loop
root.mainloop()
"
