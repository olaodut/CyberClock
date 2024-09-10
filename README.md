# Ola-DesktopClock
Clock for Desktop

# Python Desktop Clock ⏰

A simple and customizable desktop clock application built using Python and the `tkinter` library. The clock updates every second, displaying the current time in an easy-to-read format.

## Features
- 🕒 Displays the current time in `HH:MM:SS AM/PM` format.
- ⏱️ Automatically updates every second.
- 🎨 Customizable fonts, colors, and window size.
- 💻 Lightweight and runs directly on your desktop.

## Prerequisites

Before running the desktop clock, ensure that you have:

- **Python 3.x** installed. You can download Python from [python.org](https://www.python.org/downloads/).

## Installation

1. **Clone the repository**:

    ```bash
    git clone https://github.com/yourusername/python-desktop-clock.git
    ```

2. **Navigate to the project directory**:

    ```bash
    cd python-desktop-clock
    ```

3. **Run the clock application**:

    Run the Python script to launch the clock:

    ```bash
    python clock.py
    ```

## Customization

You can easily customize the clock's appearance by modifying the `clock.py` file:

### Change Font and Size:
Update the `font` parameter in the `Label` widget:
```python
label = tk.Label(root, font=('Helvetica', 50, '
