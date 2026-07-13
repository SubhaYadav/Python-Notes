# 🧪 Chapter 1 — Quiz (20 Questions)

Try to answer all 20 before scrolling to the **Answers** section at the bottom.

1. Who created Python?
2. In what year was Python first released?
3. What is Python named after?
4. What does "high-level language" mean?
5. What is CPython?
6. What is bytecode?
7. What is the Python Virtual Machine (PVM)?
8. True/False: Python code is compiled directly to machine code with no intermediate step.
9. What symbol is used for comments?
10. What does `print()` return?
11. What is PEP 8?
12. What does it mean that "everything in Python is an object"?
13. Name one non-CPython implementation of Python.
14. What is the GIL?
15. Does the GIL affect I/O-bound or CPU-bound multi-threaded programs more?
16. Why might CPython cache small integers?
17. Name one domain where Python is commonly used.
18. Name one scenario where Python might NOT be the best choice.
19. What command reveals the Zen of Python?
20. What character does Python use to define code blocks (instead of `{ }`)?

---

## ✅ Answers

1. Guido van Rossum
2. 1991
3. *Monty Python's Flying Circus* (the comedy show, not the snake)
4. A language that abstracts away hardware details and reads closer to human language
5. The default, reference implementation of Python, written in C
6. An intermediate, lower-level instruction set generated from source code, executed by the PVM
7. The runtime engine that executes bytecode instructions one at a time
8. **False** — it's compiled to bytecode first, then interpreted/executed by the PVM
9. `#`
10. `None` (it displays text as a side effect but doesn't return a usable value)
11. Python's official style guide for writing consistent, readable code
12. Every value — numbers, strings, functions, etc. — has an identity, type, and value, and is represented internally as an object
13. PyPy, Jython, or IronPython (any one is correct)
14. Global Interpreter Lock — ensures only one thread executes Python bytecode at a time in CPython
15. CPU-bound programs are affected more; I/O-bound programs are less affected since the GIL is released during I/O waits
16. As a performance optimization, since small integers are extremely common and reusing them saves memory/allocation overhead
17. Web development, data science/ML, automation/scripting, testing, or cybersecurity (any one)
18. Real-time systems, embedded firmware, or mobile app development (any one)
19. `import this`
20. Indentation (whitespace) — not a character, but consistent spacing
