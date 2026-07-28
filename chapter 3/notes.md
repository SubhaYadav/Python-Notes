# 🗒️ Chapter 3 — Quick Notes & Cheat Sheet

## Key Points

- **Script mode**: `python3 file.py` — runs a whole file top to bottom, then exits.
- **REPL (Interactive mode)**: `python3` alone — reads one line at a time, evaluates it, auto-prints the result, and loops.
- REPL = **R**ead → **E**val → **P**rint → **L**oop.
- Scripts do **not** auto-print expression results — you must call `print()` explicitly.
- Every module has a `__name__` variable: `"__main__"` when run directly, the module's own name when imported.
- `if __name__ == "__main__":` lets a file act as both a runnable script and a safely importable module.
- `print()` keyword arguments: `sep` (between arguments, default `" "`) and `end` (after everything, default `"\n"`).

## Cheat Sheet

| Command / Code | Purpose |
|---|---|
| `python3 hello.py` | Run a script file |
| `python3` | Enter the interactive REPL |
| `exit()` | Leave the REPL |
| `print("a", "b", sep="-")` | Prints `a-b` |
| `print("a", end="")` | Prints `a` with no trailing newline |
| `if __name__ == "__main__":` | Guard for script-only entry-point code |

## Common Mistakes

- Forgetting quotes around text passed to `print()`.
- Expecting a script to auto-print expression results like the REPL does.
- Running a script from the wrong working directory.
- Skipping the `__name__ == "__main__"` guard in files meant to be both run and imported.

## Frequently Asked Questions

**Q: Is the REPL just for beginners?**
No — experienced developers use it constantly to quickly test small snippets, inspect objects, or explore library behavior.

**Q: Do I need `if __name__ == "__main__":` in every single script?**
Not for tiny one-off scripts you'll never import elsewhere, but it's considered standard practice for anything that might grow or be reused.

**Q: What's the difference between `print()`'s `end` parameter and just adding `"\n"` manually?**
They achieve similar results, but `end` is the idiomatic, explicit way to control line termination without manually embedding escape characters into your string content.

## Interview Questions (Quick Recall)

1. What does REPL stand for?
2. Why does the REPL show `4` for `2 + 2` but a script doesn't?
3. What is `__name__` set to when a file runs directly?
4. Why use the `if __name__ == "__main__":` pattern?
5. What do `sep` and `end` control in `print()`?

*(Full explained answers are in `README.md` and `quiz.md`.)*
