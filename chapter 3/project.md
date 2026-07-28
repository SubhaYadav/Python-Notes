# 🛠️ Mini Project: Personalized Greeter CLI

## Goal

Build a tiny command-line "greeter" module that demonstrates script vs. import behavior, and practices `print()` formatting with `sep`/`end`.

## Requirements

1. Create a file `greeter.py` with a `main()` function.
2. `main()` should print a multi-line greeting banner using several `print()` calls, practicing `sep` and `end`.
3. Protect the script-only behavior with `if __name__ == "__main__":`.
4. Create a second file, `use_greeter.py`, that imports `greeter` and calls `greeter.main()` explicitly — proving the import itself doesn't trigger unwanted output.

## `greeter.py`

```python
def main():
    print("=" * 30)
    print("W", "E", "L", "C", "O", "M", "E", sep="")
    print("=" * 30)
    print("Hello", end=", ")
    print("friend!")
    print("Type 'exit()' anytime to leave the Python shell.")

if __name__ == "__main__":
    main()
```

Run it directly:
```bash
python3 greeter.py
```

**Expected Output:**
```
==============================
WELCOME
==============================
Hello, friend!
Type 'exit()' anytime to leave the Python shell.
```

## `use_greeter.py`

```python
import greeter

print("About to call the greeter's main() function explicitly:")
greeter.main()
```

Run it:
```bash
python3 use_greeter.py
```

**Expected Output:**
```
About to call the greeter's main() function explicitly:
==============================
WELCOME
==============================
Hello, friend!
Type 'exit()' anytime to leave the Python shell.
```

Notice that importing `greeter` in `use_greeter.py` did **not** automatically print the banner — it only appeared once `greeter.main()` was explicitly called. This proves the `if __name__ == "__main__":` guard is working correctly.

## Stretch Goals (Optional)

- Modify `greeter.py` so `main()` accepts a `name` parameter and personalizes the greeting (a small preview of Chapter 11 - Functions).
- Try running `python3 -c "import greeter; print(greeter.__name__)"` and predict the output before running it.

## What This Project Teaches

| Concept Practiced | Where it came from |
|---|---|
| Script mode execution | Chapter 3 |
| `__name__ == "__main__"` guard | Chapter 3 |
| `print()` with `sep`/`end` | Chapter 3 |
| Importing one file from another | Preview of Chapter 19 - Modules & Packages |
