# ✅ Chapter 3 — Solutions

---

## 🟢 Beginner Solutions

1. `print("Hello, World!")`
2. `python3 hello.py`
3. `python3`
4. Read–Eval–Print–Loop
5. `exit()`
6. **False** — only the REPL auto-prints expression results; scripts require explicit `print()` calls.
7. Quotation marks — either double `"..."` or single `'...'`.
8. A single space `" "`.
9. A newline character `"\n"`.
10. `__name__`

---

## 🟡 Intermediate Solutions

1. Script mode reads an entire file, compiles it, and runs it top to bottom in one go, then exits. Interactive (REPL) mode reads and executes **one line at a time**, immediately showing results, and waits for the next line.
2. The REPL automatically prints the result of any expression it evaluates as part of its Read-Eval-**Print**-Loop cycle. A script file only shows output when you explicitly call `print()` — an unprinted expression's value is simply computed and discarded.
3. `"__main__"`
4. The module's own name (e.g., `"greet"` if the file is `greet.py`).
5.
```python
if __name__ == "__main__":
    main()
```
This ensures the code inside only runs when the file is **executed directly**, not when it's **imported** by another file — letting one file safely serve as both a standalone script and a reusable module.
6. `sep` controls what string is inserted **between** multiple arguments passed to `print()`. Example: `print("a", "b", sep="-")` outputs `a-b`.
7. `end` controls what string is printed **after** all arguments, replacing the default newline. Example: `print("Loading", end="...")` outputs `Loading...` with no line break afterward.
8. Script mode is better for real, multi-step programs because you can save, edit, version-control, and re-run the entire program reliably, rather than retyping everything each session.
9. The REPL is faster for quick one-off checks — you get immediate feedback without creating, saving, and running a file.
10. Functionally, `python3` can technically execute a file regardless of extension if you pass its path directly — but `.py` is the strong convention that text editors, linters, and other tooling rely on to recognize a file as Python code; using `.txt` will confuse tooling and other developers even if the interpreter itself doesn't strictly require it.

---

## 🔴 Advanced Solutions

1. (1) You type `python3 hello.py` in your terminal. (2) The OS locates the `python3` executable via PATH and launches it, passing `hello.py` as an argument. (3) CPython reads the entire file and compiles it into bytecode. (4) The bytecode is handed to the Python Virtual Machine (PVM). (5) The PVM executes each instruction in order, including the one corresponding to `print("Hello, World!")`. (6) That instruction calls into the OS to write text to standard output. (7) Your terminal displays that text, and the interpreter process exits once the file finishes running.
2. The REPL is designed for **immediate interactive feedback** — each line's result matters right away, so it evaluates and prints line-by-line rather than waiting. Script mode is designed for **running a complete program**, so it compiles the whole file first (catching certain errors, like syntax errors, before any code runs at all) and then executes it sequentially, only showing what you explicitly print.
3.
```python
# mymodule.py
def main():
    print("Running as a script!")

print(f"Module name is: {__name__}")

if __name__ == "__main__":
    main()
```
Run directly: prints the module-name line with `__main__`, then "Running as a script!". Imported elsewhere: only the module-name line prints (showing the module's real name), and `main()` never runs.
4. Because demo/example code often performs actions with side effects (printing output, running example computations, or even opening files/network connections) that should only happen when someone deliberately runs the file as a script — not silently every time someone else's code imports a single function from that same file.
5. The network request would fire immediately and unexpectedly the moment anyone imported that module — even if all they wanted was one unrelated function from it — potentially causing duplicate requests, slow imports, or unwanted side effects far from where the import actually happens.
6. Beginners often assume `print()` and "the interpreter showing something" are the same behavior everywhere, when in fact it's specific to the REPL. This causes confusion when a script "does nothing" even though calculations *are* technically happening — they're just not displayed without an explicit `print()`.
7. Because it isolates and confirms that your **environment and toolchain** work correctly (Python installed, PATH configured, file saved and run correctly) *before* you introduce any actual program logic — separating "did my setup work" from "did my logic work" makes debugging far more tractable later.
8.
```python
print("Alice", "Bob", "Carol", sep=", ", end=".")
```
9. Because `print()`'s default `sep` argument is a single space `" "`, inserted **between** each positional argument it receives — that default behavior is what produces the single space in `Hello World`.
10. Using `exit()` or Ctrl+D signals the REPL to shut down cleanly through Python's own exit mechanism (allowing any registered cleanup code to run), whereas forcibly closing the terminal window terminates the underlying process abruptly, potentially skipping such graceful cleanup steps.

---

## 🐞 Debugging Solutions

**1.** `Hello` and `World!` aren't quoted, so Python tries to treat them as variable names (which don't exist) instead of text.
```python
print("Hello, World!")
```

**2.** Missing closing parenthesis.
```python
print("Hello, World!")
```

**3.** `=` is assignment; comparison requires `==`.
```python
if __name__ == "__main__":
    main()
```

**4.** The file either doesn't exist at that path, has a typo in its name, or you're running the command from the wrong working directory. Fix: verify the filename and `cd` into the correct folder, or provide the correct relative/absolute path.

**5.** Yes, it lands on a new line — the first `print()` call still ends with the **default** `end="\n"` (only `sep` was customized, not `end`), so a newline is still emitted after `C`.

---

## ✍️ Code Completion Solutions

**1.**
```python
print("Hello, World!")
```

**2.**
```python
print("Hello", "World", sep="-")
```

**3.**
```python
print("Loading", end="")
```

**4.**
```python
if __name__ == "__main__":
    main()
```

**5.**
```bash
python3 app.py
```

---

## 🔮 Predict the Output — Answers

**1.**
```
Hello World
```

**2.**
```
HelloWorld
```
*(The first `print` has `end=""`, so no newline is inserted between "Hello" and "World".)*

**3.**
```
A->B
```

**4.**
```
__main__
```

**5.**
```
greet
```
*(When imported, `__name__` is set to the module's own name rather than `"__main__"`.)*

---

## 🚀 Coding Challenge Solutions

**1.**
```python
name = "Ada"
print(name, end="")
print(" says hello!")
```
**Output:** `Ada says hello!`

**2.**
```python
print(2026, "07", 28, sep="-")
```
**Output:** `2026-07-28`

**3.**
```python
# greeting.py
def main():
    print("Hello!")

if __name__ == "__main__":
    main()
```

**4.**
```python
print("One ", end="")
print("Two ", end="")
print("Three")
```
**Output:** `One Two Three`

**5.**
```
>>> 5 * 5
25
>>> print("Done")
Done
>>> exit()
```
