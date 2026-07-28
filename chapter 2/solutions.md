# ✅ Chapter 2 — Solutions

---

## 🟢 Beginner Solutions

1. `python3 --version`
2. `pip3 --version`
3. Pip is Python's package manager — it downloads and installs third-party libraries (from PyPI, by default) so you can use them in your code.
4. A virtual environment is an isolated, self-contained Python setup for a single project, so its installed libraries don't affect (or get affected by) other projects.
5. `python3 -m venv venv`
6. `source venv/bin/activate`
7. `deactivate`
8. **False** — for a single throwaway script with no dependencies, a venv is optional, though still a fine habit.
9. `requirements.txt`
10. The `venv/` folder (or whatever you named it).

---

## 🟡 Intermediate Solutions

1. Activation temporarily prepends the venv's `bin`/`Scripts` folder to your shell's PATH, so when you type `python` or `pip`, your shell finds the venv's private copies **before** it finds the system-wide ones.
2. Because each project's virtual environment has its own private `site-packages` folder — Project A's copy of a library lives in a completely separate location from Project B's copy, so they never conflict.
3. It lists every package currently installed in the active environment along with its exact version number, typically redirected into a file for later reuse.
4. Run `python3 -m venv venv`, activate it, then run `pip install -r requirements.txt` — pip reads the file and installs each listed package at its specified version.
5. Installing globally affects **every** project and script on your system that uses that Python installation; installing inside an activated venv only affects that one project's isolated environment.
6. Different versions of a library can behave differently (bug fixes, breaking changes, removed features). If you don't pin/isolate versions, your teammate's globally-installed version might differ from yours, causing code that "works for them" to fail for you (or vice versa). Virtual environments + `requirements.txt` fix this by pinning and isolating exact versions per project.
7. `-m` tells Python to run a **module** as a script — here, `venv` is a module in the standard library that knows how to construct a new virtual environment.
8. It's large, contains OS-specific binaries that likely won't work on a teammate's different OS, and is entirely reproducible from `requirements.txt` — so committing it just bloats the repository with no real benefit.
9. Without a venv, all dependencies for all your projects get installed globally, risking version conflicts, "dependency hell," and making it hard to know exactly what any one project actually needs.
10. Windows PowerShell may block script execution due to its **execution policy** security setting; running PowerShell as Administrator and executing `Set-ExecutionPolicy RemoteSigned` (or an equivalent adjustment) typically resolves it.

---

## 🔴 Advanced Solutions

1. A typical `venv/` folder contains: a `bin/` (macOS/Linux) or `Scripts/` (Windows) folder with activation scripts and a Python executable reference; a `lib/` folder containing `site-packages/`, where installed libraries actually live; and configuration files (like `pyvenv.cfg`) recording which base Python interpreter the venv was built from.
2. `venv` only isolates Python packages. **conda** is a cross-language package/environment manager that can also manage non-Python dependencies (like specific compiled C libraries) and different Python versions themselves. **poetry** focuses on dependency resolution, version locking, and packaging/publishing your own project as a distributable package — solving problems venv alone doesn't address (like resolving compatible version ranges automatically).
3. It doesn't fully guarantee identical behavior across operating systems — some packages include OS-specific compiled components, and `requirements.txt` alone (without stricter tools like lockfiles) may not pin every transitive dependency identically on every OS. It's a strong step toward reproducibility, not an absolute guarantee.
4. Pinning old exact versions in `requirements.txt` can mean you never receive security patches for known vulnerabilities in that specific version. Mitigation: periodically review and update pinned versions, and use tools that scan dependencies for known vulnerabilities (e.g., `pip-audit`).
5. `pip freeze` outputs **every** installed package, including transitive dependencies pulled in automatically (like `urllib3` and `certifi` for `requests`). A hand-curated `requirements.txt` might list only the packages you directly `pip install`-ed, letting pip resolve compatible versions of the rest itself.
6. Because a venv only affects **where** packages are installed and which interpreter is used at import/setup time — once your program is running, Python bytecode execution proceeds identically regardless of which environment loaded it.
7. Recreate the venv (`python3 -m venv venv`), activate it, then run `pip install -r requirements.txt` to reinstall everything at the pinned versions.
8. Because different developers' machines often have different globally-installed package versions by default; if a project doesn't isolate and pin its dependencies, code that depends on version-specific behavior can pass on one machine and fail on another. Virtual environments + `requirements.txt` remove this ambiguity by making the dependency set explicit and reproducible.
9. You'd likely get a **permissions error** (e.g., "Permission denied" when writing to a system-protected directory), since installing outside a venv targets the global site-packages folder, which often requires elevated/admin privileges to modify.
10. Habitually using a venv avoids "just this once" exceptions that quietly turn into forgotten global installs, keeps their system-wide Python clean, and costs almost nothing in setup time — so many experienced developers default to it even when technically optional.

---

## 🐞 Debugging Solutions

**1.** On systems where `python` still points to Python 2 (or doesn't exist at all), this fails or misbehaves. Safer:
```bash
python3 -m venv venv
```

**2.** The virtual environment was likely never activated before running `pip install`, so the package went into a different (possibly global) environment than the one used to run the script. Fix: activate the venv **first**, then `pip install requests`, then run the script within that same activated shell session.

**3.** The venv might have been created using a Python 2 interpreter (if `python` pointed to Python 2 at creation time), or a stale/separate installation is still first on the PATH. Recreate the venv explicitly with `python3 -m venv venv` to ensure it's built from Python 3.

**4.** A `.gitignore` file excluding `venv/` is missing from the project. Add a `.gitignore` with a `venv/` entry.

**5.** The `requirements.txt` file lists a version of `somepkg` that doesn't exist on PyPI (perhaps a typo in the version number, or it was yanked/removed). Check PyPI for valid available versions and correct the pinned version.

---

## ✍️ Code Completion Solutions

**1.**
```bash
python3 -m venv env
```

**2.**
```bash
python3 -m pip --version
```

**3.**
```bash
pip freeze > requirements.txt
```

**4.**
```bash
pip install -r requirements.txt
```

**5.**
```
venv/
```

---

## 🔮 Predict the Output — Answers

**1.** A string in the form `Python 3.x.y` (exact numbers vary by installed version, but the format is predictable).

**2.** A **short/mostly-empty-ish** list — a brand-new venv typically starts with just `pip` and `setuptools` (and sometimes `wheel`), not a long list, since no third-party packages have been installed yet.

**3.** It would show `requests` **plus its dependencies** (e.g., `urllib3`, `certifi`, `idna`, `charset-normalizer`), since `pip freeze` lists everything installed in the environment, not just what you explicitly typed.

**4.** **Not valid as written** — `python3 -m venv` requires a target directory name as an argument (e.g., `python3 -m venv venv`); running it with no name will produce a usage/error message.

**5.** After `deactivate`, `pip list` shows the **system-wide** packages, since your shell's PATH has been restored to point at the global Python/pip rather than the venv's private copies.

---

## 🚀 Coding Challenge Solutions

**1.**
```bash
mkdir my_project
cd my_project
python3 -m venv venv
source venv/bin/activate
pip install requests
pip freeze > requirements.txt
```

**2.**
```bash
git clone <repo-url>
cd <repo-folder>
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

**3.**
```
venv/
__pycache__/
```

**4.**
```bash
pip show requests
# or
pip list
```

**5.** Running `pip install pandas` without an active virtual environment on a shared or production machine installs the package **globally**, potentially overwriting a version another application on that machine depends on, or upgrading a dependency in a way that silently breaks unrelated software that assumed the older version's behavior — this is why isolating installs per project via a venv is strongly recommended, especially outside your personal development laptop.
