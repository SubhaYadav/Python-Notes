# 🏋️ Chapter 3 — Practice

> Attempt every question before checking [`solutions.md`](./solutions.md).

---

## 🟢 Beginner (10 Questions)

1. Write the single line of Python code that prints `Hello, World!`.
2. What terminal command runs a script named `hello.py`?
3. What terminal command opens the interactive Python shell?
4. What does REPL stand for?
5. What command exits the REPL?
6. True or False: A script file automatically prints the result of every expression, just like the REPL.
7. What symbol/quotes are needed around text passed to `print()`?
8. What is the default separator `print()` uses between multiple arguments?
9. What is the default value printed after `print()`'s output (i.e., what character ends each print by default)?
10. What variable does every Python module have that tells you whether it's being run directly or imported?

---

## 🟡 Intermediate (10 Questions)

1. Explain the difference between script mode and interactive (REPL) mode.
2. Why does typing `2 + 2` in the REPL show `4`, but the same line inside a `.py` script shows nothing unless wrapped in `print()`?
3. What value does `__name__` hold when a file is run directly with `python3 file.py`?
4. What value does `__name__` hold when that same file is imported by another file?
5. Write the `if __name__ == "__main__":` pattern and explain, in your own words, what problem it solves.
6. What does the `sep` parameter of `print()` do? Give an example.
7. What does the `end` parameter of `print()` do? Give an example.
8. Why might you prefer script mode over the REPL for a real, multi-step program?
9. Why might you prefer the REPL over a script file when quickly testing a one-line library call?
10. What's the practical difference between saving code as `hello.py` vs. `hello.txt` when you intend to run it with Python?

---

## 🔴 Advanced (10 Questions)

1. Walk through, step by step, everything that happens between typing `python3 hello.py` in a terminal and seeing `Hello, World!` printed.
2. Why does the REPL evaluate and print results line-by-line instead of waiting to compile the entire session at once, and how does this relate to how script mode compiles a whole file before running it?
3. Design a small module that behaves differently when imported vs. run directly, using `__name__`, and explain each behavior.
4. Explain why frameworks and libraries almost universally protect their example/demo code with `if __name__ == "__main__":` rather than just letting demo code run at import time.
5. What would happen (in terms of unwanted side effects) if a module performed real work (e.g., sending a network request) directly at the top level, without any `__name__` guard, and another file simply tried to import one function from it?
6. Compare the mental model of "print() explicitly displays text" versus "the REPL auto-displays results" — why is this distinction one of the most common sources of beginner confusion?
7. Why is verifying "Hello, World!" runs correctly considered a meaningful debugging step, even though the program itself does nothing useful?
8. If you wanted to print three names on the same line separated by commas and a space, but ending with a period and no trailing newline, how would you construct that single `print()` call using `sep` and `end`?
9. Explain why `print("Hello", "World")` produces `Hello World` (with one space) rather than `HelloWorld` or `Hello  World` (two spaces).
10. Why does closing the REPL with `exit()` or Ctrl+D differ conceptually from just closing the terminal window entirely (in terms of what "gracefully exiting" means for a running program)?

---

## 🐞 Debugging Problems (5)

**1.**
```python
print(Hello, World!)
```

**2.**
```python
print("Hello, World!"
```

**3.**
```python
def main():
    print("Hello, World!")

if __name__ = "__main__":
    main()
```

**4.**
```bash
python3 hello.py
# python3: can't open file 'hello.py': [Errno 2] No such file or directory
```

**5.**
```python
print("A", "B", "C", sep="")
print("still on new line?")
```
*(Predict: does the second print land on a new line or not, and why?)*

---

## ✍️ Code Completion Problems (5)

**1.** Complete the code to print `Hello, World!`.
```python
____("Hello, World!")
```

**2.** Complete the code so the two words print with a hyphen between them: `Hello-World`.
```python
print("Hello", "World", sep=____)
```

**3.** Complete the code so this print does NOT end with a newline.
```python
print("Loading", end=____)
```

**4.** Complete the guard so `main()` only runs when the file is executed directly.
```python
if __name__ == ____:
    main()
```

**5.** Complete the command to run a script named `app.py`.
```bash
____ app.py
```

---

## 🔮 Predict the Output (5)

**1.**
```python
print("Hello", "World")
```

**2.**
```python
print("Hello", end="")
print("World")
```

**3.**
```python
print("A", "B", sep="->")
```

**4.**
```python
# saved as greet.py, run directly
print(__name__)
```

**5.**
```python
# saved as greet.py, then imported elsewhere as "import greet"
print(__name__)
```
*(What prints, assuming the import happens from a different file?)*

---

## 🚀 Coding Challenges (5)

1. Write a script that prints your name, then on the same line (no newline in between) prints " says hello!".
2. Write a script using a single `print()` call with `sep` to output `2026-07-28` from the values `2026`, `07`, `28`.
3. Write a module `greeting.py` with a `main()` function that prints "Hello!", guarded properly so importing the module doesn't trigger the print.
4. Write a script that prints three separate `print()` calls, but makes all three appear on a single output line using `end=""` appropriately.
5. Write a short REPL session (as text, showing `>>>` prompts) where you compute `5 * 5`, then print `"Done"`, then exit.
