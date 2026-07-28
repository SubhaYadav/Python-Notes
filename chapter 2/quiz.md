# 🧪 Chapter 2 — Quiz (20 Questions)

Try to answer all 20 before scrolling to the **Answers** section at the bottom.

1. What command checks your installed Python 3 version?
2. What is `pip`?
3. What is a virtual environment, in one sentence?
4. What command creates a virtual environment named `venv`?
5. What command activates a venv on macOS/Linux?
6. What command activates a venv on Windows PowerShell?
7. What command exits an active virtual environment?
8. What file typically records a project's exact dependency versions?
9. What command generates that file from an active environment's installed packages?
10. What command installs packages listed in that file?
11. What folder should always be added to `.gitignore` after creating a venv?
12. What actually changes in your shell when you "activate" a venv?
13. Why can two projects use conflicting versions of the same library safely?
14. What is the `-m` flag doing in `python3 -m venv venv`?
15. Name one third-party alternative/complement to `venv` that also manages dependency resolution or packaging.
16. Does creating/activating a venv add runtime overhead to your program's execution speed?
17. What kind of error might you see if a `requirements.txt` references a version that doesn't exist on PyPI?
18. What's the risk of installing packages globally on a shared production machine?
19. True/False: `pip freeze` only lists packages you explicitly typed `pip install` for, not their dependencies.
20. What OS-specific Windows setting might block venv activation scripts, and how do you fix it?

---

## ✅ Answers

1. `python3 --version`
2. Python's standard package manager, used to install third-party libraries from PyPI (or other sources)
3. An isolated, self-contained Python setup for one project, so its dependencies don't conflict with other projects
4. `python3 -m venv venv`
5. `source venv/bin/activate`
6. `venv\Scripts\Activate.ps1`
7. `deactivate`
8. `requirements.txt`
9. `pip freeze > requirements.txt`
10. `pip install -r requirements.txt`
11. `venv/` (or whatever name you gave the environment folder)
12. Your shell's PATH is temporarily modified so `python`/`pip` resolve to the venv's private copies instead of the system-wide installation
13. Because each venv has its own private `site-packages` folder, completely separate from other projects' environments
14. It tells Python to run the `venv` standard library module as a script, which constructs the new virtual environment
15. `conda` or `poetry` (either is correct)
16. No — it only affects where packages are installed/found; it has no effect on runtime execution speed
17. A "could not find a version that satisfies the requirement" style error from pip
18. It can overwrite or upgrade a version another application on that machine depends on, silently breaking unrelated software
19. **False** — it lists every installed package, including transitive dependencies pulled in automatically
20. PowerShell's execution policy can block script execution; running PowerShell as Administrator and using `Set-ExecutionPolicy RemoteSigned` (or an appropriate equivalent) typically resolves it
