import tkinter as tk
from tkinter import messagebox

class Calculator:
    def __init__(self, root):
        self.root = root
        self.root.title("Simple Calculator")
        self.root.geometry("410x410")
        
        # Entry widget for input and output
        self.entry = tk.Entry(root, font=("Arial", 20), borderwidth=2, relief="solid", justify="right")
        self.entry.grid(row=0, column=0, columnspan=4, pady=10, padx=10, ipadx=5, ipady=10)

        # Buttons
        self.create_buttons()

    def create_buttons(self):
        """Creates calculator buttons."""
        buttons = [
            ('7', 1, 0), ('8', 1, 1), ('9', 1, 2), ('/', 1, 3),
            ('4', 2, 0), ('5', 2, 1), ('6', 2, 2), ('*', 2, 3),
            ('1', 3, 0), ('2', 3, 1), ('3', 3, 2), ('-', 3, 3),
            ('C', 4, 0), ('0', 4, 1), ('=', 4, 2), ('+', 4, 3),
        ]

        for (text, row, col) in buttons:
            button = tk.Button(
                self.root, text=text, font=("Arial", 18), width=5, height=2,
                command=lambda t=text: self.on_button_click(t)
            )
            button.grid(row=row, column=col, padx=5, pady=5)

    def on_button_click(self, char):
        """Handles button clicks."""
        if char == 'C':  # Clear the entry
            self.entry.delete(0, tk.END)
        elif char == '=':  # Evaluate the expression
            try:
                result = eval(self.entry.get())
                self.entry.delete(0, tk.END)
                self.entry.insert(tk.END, str(result))
            except Exception:
                messagebox.showerror("Error", "Invalid Expression")
        else:  # Append the character to the entry
            self.entry.insert(tk.END, char)

# Main program
if __name__ == "__main__":
    root = tk.Tk()
    calc = Calculator(root)
    root.mainloop()
