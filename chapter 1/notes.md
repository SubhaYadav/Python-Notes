# 🗒️ Chapter 1 — Quick Notes & Cheat Sheet

## Key Points

- Python = high-level, interpreted, general-purpose language.
- Created by **Guido van Rossum**, released **1991**.
- Named after *Monty Python's Flying Circus*, not the snake.
- **CPython** = the default implementation (written in C).
- Code flow: `.py` source → **bytecode** → **Python Virtual Machine (PVM)** → machine code.
- Everything in Python is an **object** (numbers, strings, functions, everything).
- Variables are **names/labels** pointing to objects, not boxes holding raw values.
- Python uses **indentation** (not braces) to define code blocks.
- CPython has a **Global Interpreter Lock (GIL)** — one thread runs Python bytecode at a time.
- `import this` → prints *The Zen of Python* (design philosophy, 19 aphorisms).

## Cheat Sheet

| Concept | One-liner |
|---|---|
| Interpreter | Program that reads and executes your code (via bytecode + PVM) |
| Bytecode | Intermediate instructions between source code and machine code |
| CPython | The reference/default Python implementation, written in C |
| PEP 8 | Python's official style guide |
| `id(obj)` | Returns the memory address of an object |
| Comment | `# this is a comment` |

## Common Mistakes

- Mixing tabs and spaces for indentation.
- Forgetting the trailing `:` on `if`, `for`, `while`, `def`, `class` lines.
- Assuming `print()` returns a value (it doesn't — it displays and returns `None`).
- Running `python` instead of `python3` on systems where both exist.

## Frequently Asked Questions

**Q: Do I need to know C to understand how Python works internally?**
No. This course explains internals in plain English with diagrams — no prior systems knowledge required.

**Q: Is Python 2 still relevant?**
No — Python 2 reached end-of-life in January 2020. This entire course uses **Python 3**.

**Q: Why does Python use indentation instead of braces?**
It's a deliberate design choice to force consistent, readable formatting — "readability counts" is literally one of the Zen of Python principles.

## Interview Questions (Quick Recall)

1. Who created Python and when?
2. What does "interpreted" mean in Python's context?
3. What is the PVM?
4. Name two non-CPython implementations of Python.
5. What is the GIL?

*(Full explained answers are in `README.md` and `quiz.md`.)*
