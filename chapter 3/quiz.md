# 🧪 Chapter 3 — Quiz (20 Questions)

Try to answer all 20 before scrolling to the **Answers** section at the bottom.

1. What line of code prints `Hello, World!`?
2. What command runs a script file named `hello.py`?
3. What command opens Python's interactive shell?
4. What does REPL stand for?
5. What command exits the REPL?
6. Does a script file automatically print expression results like the REPL does?
7. What quotes/symbols must surround text passed to `print()`?
8. What is `print()`'s default separator between multiple arguments?
9. What is `print()`'s default value for what comes after the output?
10. What variable tells you whether a file is being run directly or imported?
11. What is `__name__` set to when a file is run directly?
12. What is `__name__` set to when a file is imported?
13. Write the standard guard pattern used to protect script-only code.
14. What does the `sep` parameter of `print()` control?
15. What does the `end` parameter of `print()` control?
16. Why is script mode generally preferred over the REPL for real, multi-step programs?
17. Why is the REPL preferred for quick, one-off checks?
18. What's the practical convention reason for saving Python files with a `.py` extension?
19. What's the output of `print("A", "B", sep="", end="!")`?
20. Why is "Hello, World!" considered a meaningful first debugging step, despite doing nothing useful on its own?

---

## ✅ Answers

1. `print("Hello, World!")`
2. `python3 hello.py`
3. `python3` (with no filename argument)
4. Read–Eval–Print–Loop
5. `exit()`
6. No — only the REPL auto-prints expression results; scripts require explicit `print()` calls
7. Double or single quotes: `"..."` or `'...'`
8. A single space `" "`
9. A newline `"\n"`
10. `__name__`
11. `"__main__"`
12. The module's own name (e.g., `"greet"`)
13. `if __name__ == "__main__":`
14. What string is inserted **between** multiple arguments passed to `print()`
15. What string is printed **after** all the arguments, replacing the default newline
16. Because it's saveable, editable, version-controllable, and reliably re-runnable, unlike REPL sessions
17. Because it gives immediate feedback for small snippets without the overhead of creating and running a file
18. Editors, linters, and other tools rely on the `.py` extension to recognize and properly handle Python code
19. `AB!` (no space due to empty `sep`, no newline due to custom `end`)
20. It verifies your entire toolchain (interpreter installed, PATH configured, file saved/run correctly) works *before* you introduce real program logic, isolating setup problems from logic problems
