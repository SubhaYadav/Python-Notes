# 🗒️ Chapter 2 — Quick Notes & Cheat Sheet

## Key Points

- **Python interpreter** = the program (`python3`) that runs your `.py` files.
- **pip** = Python's package manager (installs libraries from PyPI).
- **venv** = Python's built-in tool for creating isolated, per-project environments.
- A virtual environment is just a folder with a private interpreter reference + private `site-packages`.
- Activating a venv temporarily changes your shell's PATH so `python`/`pip` point at the private copies.
- `pip freeze > requirements.txt` captures exact installed versions for reproducibility.
- `pip install -r requirements.txt` recreates an environment from that file.

## Cheat Sheet

| Command | Purpose |
|---|---|
| `python3 --version` | Check installed Python version |
| `pip3 --version` | Check installed pip version |
| `python3 -m venv venv` | Create a virtual environment named `venv` |
| `source venv/bin/activate` | Activate venv (macOS/Linux) |
| `venv\Scripts\Activate.ps1` | Activate venv (Windows PowerShell) |
| `deactivate` | Exit the active venv |
| `pip install <package>` | Install a package into the active environment |
| `pip freeze > requirements.txt` | Save exact installed versions |
| `pip install -r requirements.txt` | Install from a saved requirements file |

## Common Mistakes

- Using `python`/`pip` instead of `python3`/`pip3` on systems with both Python 2 and 3.
- Forgetting to activate the venv before installing packages.
- Committing the `venv/` folder to Git instead of `.gitignore`-ing it.
- Installing packages globally, causing version conflicts between projects.

## Frequently Asked Questions

**Q: Do I need a virtual environment for every single script?**
Not strictly for a one-off throwaway script with no dependencies, but it's good habit-forming to always use one.

**Q: What's the difference between `venv` and tools like `conda` or `poetry`?**
`venv` is Python's built-in, lightweight option. `conda` and `poetry` are third-party tools with extra features (cross-language package management for conda, dependency resolution and packaging for poetry) — out of scope for this beginner chapter but worth knowing they exist.

**Q: Can I name my virtual environment folder something other than `venv`?**
Yes — `venv` is just a convention. `python3 -m venv myenv` works identically, just adjust activation paths accordingly.

## Interview Questions (Quick Recall)

1. What problem does a virtual environment solve?
2. What is `pip`?
3. What does `pip freeze` do?
4. What actually changes when you "activate" a venv?
5. Why shouldn't you commit `venv/` to version control?

*(Full explained answers are in `README.md` and `quiz.md`.)*
