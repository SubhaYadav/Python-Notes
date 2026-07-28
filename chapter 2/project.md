# 🛠️ Mini Project: "Project Starter Kit" Setup Script

## Goal

Apply everything from Chapter 2 by setting up a properly isolated Python project from scratch, exactly the way professional developers start new projects.

## Requirements

1. Create a new project folder called `starter_kit`.
2. Create and activate a virtual environment inside it.
3. Install the `requests` library into that environment.
4. Write a tiny Python script, `check_setup.py`, that imports `requests` and prints its version — confirming the environment works.
5. Freeze your installed packages into `requirements.txt`.
6. Create a `.gitignore` file excluding `venv/` and `__pycache__/`.

## Step-by-Step (Terminal Commands)

```bash
# 1. Create and enter the project folder
mkdir starter_kit
cd starter_kit

# 2. Create and activate the virtual environment
python3 -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\Activate.ps1

# 3. Install a library
pip install requests

# 4. Save dependencies
pip freeze > requirements.txt
```

## `check_setup.py`

```python
import requests

print("Environment is working!")
print(f"requests library version: {requests.__version__}")
```

Run it:
```bash
python3 check_setup.py
```

**Expected Output (version may vary):**
```
Environment is working!
requests library version: 2.31.0
```

## `.gitignore`

```
venv/
__pycache__/
```

## Stretch Goals (Optional)

- Add a second dependency (e.g., `rich` for colorful terminal output) and update `requirements.txt`.
- Write a short `README.md` for your `starter_kit` project explaining how a new contributor would set it up (this previews good open-source practices from later chapters).
- Try deleting your `venv/` folder entirely, then recreate it using only `requirements.txt`, to prove to yourself that the environment is fully reproducible.

## What This Project Teaches

| Concept Practiced | Where it came from |
|---|---|
| Creating a virtual environment | Chapter 2 |
| Activating/deactivating an environment | Chapter 2 |
| Installing a third-party package | Chapter 2 |
| Freezing and restoring dependencies | Chapter 2 |
| Importing an external library in code | Preview of Chapter 19 - Modules & Packages |
| Writing a `.gitignore` | General open-source best practice |
