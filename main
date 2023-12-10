import tkinter as tk
from tkinter import messagebox
import pyperclip

def generate_mla_citation(title, author, publisher, year, edition=None, volume=None, pages=None, url=None):
    citation = f'{author}. "{title}." {publisher}, {year}'
    
    if edition:
        citation += f', {edition} ed.'
    if volume:
        citation += f', vol. {volume}'
    if pages:
        citation += f', pp. {pages}'
    if url:
        citation += f', {url}'

    citation += '.'
    return citation

def submit_form():
    title = entry_title.get()
    author = entry_author.get()
    publisher = entry_publisher.get()
    year = entry_year.get()
    edition = entry_edition.get()
    volume = entry_volume.get()
    pages = entry_pages.get()
    url = entry_url.get()

    if not title or not author or not publisher or not year:
        messagebox.showerror("Error", "Please fill in at least Title, Author, Publisher, and Year.")
    else:
        citation = generate_mla_citation(title, author, publisher, year, edition, volume, pages, url)
        result_text.config(state=tk.NORMAL)
        result_text.delete("1.0", tk.END)
        result_text.insert(tk.END, citation)
        result_text.config(state=tk.DISABLED)

def copy_to_clipboard():
    citation = result_text.get("1.0", tk.END)
    pyperclip.copy(citation)
    messagebox.showinfo("Copied", "MLA Citation copied to clipboard.")

def clear_form():
    entry_title.delete(0, tk.END)
    entry_author.delete(0, tk.END)
    entry_publisher.delete(0, tk.END)
    entry_year.delete(0, tk.END)
    entry_edition.delete(0, tk.END)
    entry_volume.delete(0, tk.END)
    entry_pages.delete(0, tk.END)
    entry_url.delete(0, tk.END)
    result_text.config(state=tk.NORMAL)
    result_text.delete("1.0", tk.END)
    result_text.config(state=tk.DISABLED)

# Create the main window
window = tk.Tk()
window.title("MLA Citation Generator")

# Create and place form elements
tk.Label(window, text="Title:").grid(row=0, column=0, padx=10, pady=5, sticky="e")
tk.Label(window, text="Author:").grid(row=1, column=0, padx=10, pady=5, sticky="e")
tk.Label(window, text="Publisher:").grid(row=2, column=0, padx=10, pady=5, sticky="e")
tk.Label(window, text="Year:").grid(row=3, column=0, padx=10, pady=5, sticky="e")
tk.Label(window, text="Edition:").grid(row=4, column=0, padx=10, pady=5, sticky="e")
tk.Label(window, text="Volume:").grid(row=5, column=0, padx=10, pady=5, sticky="e")
tk.Label(window, text="Pages:").grid(row=6, column=0, padx=10, pady=5, sticky="e")
tk.Label(window, text="URL:").grid(row=7, column=0, padx=10, pady=5, sticky="e")

entry_title = tk.Entry(window)
entry_author = tk.Entry(window)
entry_publisher = tk.Entry(window)
entry_year = tk.Entry(window)
entry_edition = tk.Entry(window)
entry_volume = tk.Entry(window)
entry_pages = tk.Entry(window)
entry_url = tk.Entry(window)

entry_title.grid(row=0, column=1, padx=10, pady=5, columnspan=2)
entry_author.grid(row=1, column=1, padx=10, pady=5, columnspan=2)
entry_publisher.grid(row=2, column=1, padx=10, pady=5, columnspan=2)
entry_year.grid(row=3, column=1, padx=10, pady=5, columnspan=2)
entry_edition.grid(row=4, column=1, padx=10, pady=5, columnspan=2)
entry_volume.grid(row=5, column=1, padx=10, pady=5, columnspan=2)
entry_pages.grid(row=6, column=1, padx=10, pady=5, columnspan=2)
entry_url.grid(row=7, column=1, padx=10, pady=5, columnspan=2)

# Create and place the submit button
submit_button = tk.Button(window, text="Generate Citation", command=submit_form)
submit_button.grid(row=8, column=0, pady=10)

# Create and place the result text box
result_text = tk.Text(window, height=5, width=40, state=tk.DISABLED)
result_text.grid(row=8, column=1, columnspan=2, pady=10)

# Create and place the copy button
copy_button = tk.Button(window, text="Copy to Clipboard", command=copy_to_clipboard)
copy_button.grid(row=9, column=0, columnspan=3, pady=10)

# Create and place the clear button
clear_button = tk.Button(window, text="Clear Inputs", command=clear_form)
clear_button.grid(row=10, column=0, columnspan=3, pady=10)

# Run the GUI
window.mainloop()
