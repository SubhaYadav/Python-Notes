# 🛠️ Mini Project: "About Me" Console Card

## Goal

Apply everything from Chapter 1 — `print()`, comments, f-strings, and basic program flow — to build a tiny program that prints a formatted "About Me" card to the console.

## Requirements

1. Store your name, age, favorite language, and one fun fact in variables.
2. Use comments to label each section of your code.
3. Use an f-string to build a nicely formatted output.
4. Print a bordered "card" using `print()`, like this:

```
==============================
        ABOUT ME
==============================
Name        : Ada
Age         : 28
Language    : Python
Fun Fact    : Wrote the first computer algorithm.
==============================
```

## Starter Code

```python
# ---- About Me Card ----
# Step 1: store your details
name = "Ada"
age = 28
language = "Python"
fun_fact = "Wrote the first computer algorithm."

# Step 2: build the card using an f-string and print statements
print("=" * 30)
print("        ABOUT ME")
print("=" * 30)
print(f"Name        : {name}")
print(f"Age         : {age}")
print(f"Language    : {language}")
print(f"Fun Fact    : {fun_fact}")
print("=" * 30)
```

## Stretch Goals (Optional)

- Use a **list** to store multiple fun facts and print all of them (previews Chapter 13 - Arrays).
- Wrap the card-printing logic in a **function** called `print_about_me()` (previews Chapter 11 - Functions).
- Add an `if` statement that prints a different message depending on whether `age >= 18` (previews Chapter 09 - Conditional Statements).

## What This Project Teaches

| Concept Practiced | Where it came from |
|---|---|
| Variables holding text/numbers | Chapter 1 preview |
| `print()` function | Chapter 1 |
| f-strings | Chapter 1 |
| Comments | Chapter 1 |
| String repetition with `*` | Bonus — a preview of Chapter 14 - Strings |

This project intentionally previews ideas from later chapters — don't worry about mastering them yet. The goal is just to get comfortable running a real Python file end-to-end.
