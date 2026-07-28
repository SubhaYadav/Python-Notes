# 🏋️ Chapter 2 — Practice

> Attempt every question before checking [`solutions.md`](./solutions.md).

---

## 🟢 Beginner (10 Questions)

1. What command checks your installed Python version?
2. What command checks your installed pip version?
3. What does "pip" stand for/do, in your own words?
4. What is a virtual environment, in one sentence?
5. What command creates a virtual environment named `venv`?
6. What command activates a virtual environment on macOS/Linux?
7. What command deactivates an active virtual environment?
8. True or False: You must always use a virtual environment, even for a single-line throwaway script.
9. What file is commonly used to record a project's exact dependency versions?
10. What folder should you add to `.gitignore` after creating a virtual environment?

---

## 🟡 Intermediate (10 Questions)

1. Explain what actually happens on your computer's PATH when you activate a virtual environment.
2. Why can two different projects safely use two different versions of the same library?
3. What is the purpose of `pip freeze`?
4. How would you recreate an identical environment on a new machine using `requirements.txt`?
5. What's the difference between installing a package globally vs. inside an activated venv?
6. Why might a teammate's code fail on your machine even though it "works for them" — and how do virtual environments/requirements files help prevent this?
7. What does the `-m` flag do in `python3 -m venv venv`?
8. Why is it considered bad practice to commit a `venv/` folder to Git?
9. What's one downside of NOT using a virtual environment for a real, multi-dependency project?
10. On Windows, what issue might block venv activation in PowerShell, and how can you resolve it?

---

## 🔴 Advanced (10 Questions)

1. Describe, in detail, the folder structure created inside a `venv/` directory and what each part is for.
2. Compare `venv` with `conda` and `poetry` at a conceptual level — what extra problems do the latter two try to solve?
3. Why does `pip install -r requirements.txt` guarantee (or not guarantee) the exact same behavior across two different operating systems?
4. Explain a scenario where pinning exact versions in `requirements.txt` could actually cause a security problem, and how you might mitigate it.
5. What's the difference between `pip freeze` output and a hand-written `requirements.txt` that only lists direct dependencies (not transitive ones)?
6. Why doesn't creating or activating a virtual environment have any runtime performance cost on your actual program's execution speed?
7. If you delete a project's `venv/` folder entirely, what do you need to do to get the project running again, assuming you have `requirements.txt`?
8. Explain why "it works on my machine" bugs often trace back to dependency management, and how this chapter's tools address that.
9. What would happen if you tried to `pip install` a package while a venv was NOT activated, on a system without proper permissions — what class of error might occur, and why?
10. Why might an experienced developer choose to use a virtual environment even for a "quick one-off script" despite the chapter mentioning it's optional?

---

## 🐞 Debugging Problems (5)

**1.**
```bash
python -m venv venv
```
*(Works on some systems, fails or gives Python 2 behavior on others — what's the safer command?)*

**2.**
```bash
pip install requests
python3 my_script.py
# ModuleNotFoundError: No module named 'requests'
```
*(Package was clearly installed — what step was likely skipped?)*

**3.**
```bash
source venv/bin/activate
# still shows Python 2.7 when running python3 --version
```
*(What might be misconfigured?)*

**4.**
```
git status
# shows hundreds of changed files inside venv/
```
*(What's missing from the project setup?)*

**5.**
```bash
pip install -r requirements.txt
# ERROR: Could not find a version that satisfies the requirement somepkg==99.99.99
```
*(What does this error suggest about the requirements file?)*

---

## ✍️ Code Completion Problems (5)

**1.** Complete the command to create a venv named `env` instead of `venv`.
```bash
python3 -m venv ____
```

**2.** Complete the command to check pip's version explicitly through Python 3.
```bash
python3 -m ____ --version
```

**3.** Complete the command to save currently installed packages to a file.
```bash
pip freeze > ____
```

**4.** Complete the command to install from a saved requirements file.
```bash
pip install ____ requirements.txt
```

**5.** Complete the `.gitignore` entry to exclude a virtual environment folder named `venv`.
```
____
```

---

## 🔮 Predict the Output (5)

**1.**
```bash
python3 --version
```
*(What TYPE of output do you expect, even without knowing the exact version number?)*

**2.**
```bash
python3 -m venv venv
source venv/bin/activate
pip list
```
*(What would `pip list` show right after creating a brand-new venv — a long list or a short/empty-ish one?)*

**3.**
```bash
pip install requests
pip freeze
```
*(Would the output show only `requests`, or `requests` plus its dependencies?)*

**4.**
```bash
deactivate
python3 -m venv
```
*(Is this command valid as written? Why or why not?)*

**5.**
```bash
source venv/bin/activate
deactivate
pip list
```
*(After deactivating, does `pip list` show the venv's packages or the system-wide ones?)*

---

## 🚀 Coding Challenges (5)

1. Write the full sequence of terminal commands to: create a project folder, create a venv inside it, activate it, install `requests`, and save a `requirements.txt`.
2. Write the terminal commands a new teammate would run to clone your project and recreate the exact same environment from your `requirements.txt`.
3. Write a `.gitignore` file (just the relevant lines) that excludes a `venv/` folder and Python's `__pycache__/` folders.
4. Write the commands to check whether `requests` is installed inside the currently active environment, without opening a Python file (hint: think about `pip show` or `pip list`).
5. Write a short explanation (as if teaching a beginner) of why running `pip install pandas` without an active virtual environment on a shared/production machine could be risky.
