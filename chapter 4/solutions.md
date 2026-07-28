# ✅ Chapter 4 — Solutions

---

## 🟢 Beginner Solutions

1. Indentation (whitespace).
2. `#`
3. A colon `:`.
4. **True**.
5. **No** — identifiers cannot start with a digit.
6. **No** — `class` is a reserved keyword used to define classes, so Python's grammar won't allow it as a variable name.
7. **4 spaces**.
8. Backslash `\`.
9. `TabError`.
10. It's **legal** but **not recommended** — PEP 8 favors one statement per line for readability.

---

## 🟡 Intermediate Solutions

1. Python looks at each line's leading whitespace. When indentation increases after a line ending in `:`, a new block begins. When indentation decreases, the current block(s) close, back to the matching earlier indentation level.
2. They're special internal tokens CPython's tokenizer generates to mark "a new indented block begins here" (`INDENT`) and "this indented block ends here" (`DEDENT`) — functioning like implicit versions of `{` and `}`.
3. Because Python can't reliably determine whether a tab and a certain number of spaces represent the *same* indentation depth or not — the ambiguity is unsafe to silently guess at, so Python 3 raises an explicit error instead.
4. Any three of: may only contain letters, digits, and underscores; cannot start with a digit; cannot be a reserved keyword; are case-sensitive.
5. A keyword is a word reserved by Python's own grammar for a specific syntactic purpose (like `if`, `class`, `return`). Reusing one as a variable name would create ambiguity the parser can't resolve, so Python disallows it entirely.
6. Parentheses: `total = (1 + 2 +\n 3)`. Backslash: `total = 1 + 2 + \\\n 3`.
7. Because backslash continuation is fragile — a stray trailing space after the `\` silently breaks it (and the error can be confusing) — while parentheses-based continuation has no such hidden pitfall and is visually clearer.
8. Comments are stripped out entirely during compilation to bytecode — they never become part of what actually executes, so they cannot add any runtime cost.
9. Example: `x = 5  # set x to 5` — it just restates what the code already obviously shows, adding no new information for a reader.
10. An inline comment shares a line with code: `x = 5  # store age`. A full-line comment occupies its own line: `# This section handles user input`.

---

## 🔴 Advanced Solutions

1. As the tokenizer scans line by line, it measures each line's leading whitespace. Whenever that measurement increases relative to the previous logical line (and the previous line ended with a colon), it emits an `INDENT` token. Whenever it decreases, it emits one or more `DEDENT` tokens to close out the corresponding block(s) — these tokens are then used by the parser to build the code's actual block structure, the same conceptual role played by `{`/`}` in brace-based languages.
2. Developers from brace-based languages sometimes find whitespace-based syntax unfamiliar or worry that invisible whitespace differences (like tabs vs. spaces) could cause silent bugs. The counterargument: because Python *enforces* consistent indentation as an actual syntax rule (raising errors on ambiguity, like `TabError`), it eliminates an entire class of bugs common in brace-based languages, where indentation can visually mislead a reader even though the braces say something different (e.g., the classic "dangling-else" confusion).
3. An `IndentationError` (or `TabError`) occurs when indentation is genuinely ambiguous or inconsistent within what should be one block — e.g., two sibling lines in the same block using different indentation widths. A *logically different but still valid* case would be indenting a line one level less than intended — Python parses it as a completely valid but different block structure (e.g., accidentally placing a line outside an `if` block instead of inside it), with no error at all, just wrong behavior — which is often more dangerous because it fails silently.
4. Because a traceback normally reports a specific **line number** where an error occurred; when several statements are packed onto one line via semicolons, that single line number no longer clearly identifies which specific statement among several actually failed, adding an extra step to your debugging process.
5. This would be **illegal** — Python requires all statements within the *same* block to share the *same* indentation width; a mismatch between the `if` body and its matching `else` body (assuming they're meant to be siblings within their respective blocks) would raise an `IndentationError`.
6. Because they exist only in the source `.py` text; the compilation stage (source → bytecode) strips comments and whitespace/indentation entirely, converting only actual instructions and their block structure into bytecode operations — this is precisely why they add zero runtime cost.
7. Tab-based indentation risks inconsistent rendering/behavior across different editors/team members' configurations, and awkwardly-continued long lines hurt readability in code review — both directly impact how easily a team can collaborate on and trust shared code.
8. Python's colon+indentation approach makes the *visual* structure of the code and its *actual* logical structure the same thing by construction, which prevents bugs where code visually looks like it's inside a block (due to misleading indentation) but the braces say otherwise (a classic source of real-world bugs in brace-based languages, since indentation there is just a style convention, not enforced truth).
9. Because a stray space accidentally typed after a trailing backslash silently breaks the continuation (the backslash is no longer the very last character on the line), often producing a confusing syntax error far from the actual mistake; parentheses-based continuation has no equivalent "invisible trailing character" failure mode.
10. Case-sensitivity means `Age` and `age` are treated as two completely separate variables. A realistic beginner bug: defining `Name = "Ada"` at the top of a script, then later trying to use `name` (lowercase) elsewhere, resulting in a `NameError` because `name` was never actually defined — only `Name` was.

---

## 🐞 Debugging Solutions

**1.** Missing colon after `if True`.
```python
if True:
    print("yes")
```

**2.** Function body isn't indented.
```python
def greet():
    print("hi")
```

**3.** Inconsistent indentation — `print("b")` uses more indentation than its sibling `print("a")`.
```python
if True:
    print("a")
    print("b")
```

**4.** `class` is a reserved keyword and cannot be used as a variable name.
```python
course = "Math101"
print(course)
```

**5.** There's likely trailing whitespace after the backslash on the second line (invisible in most editors), which breaks the continuation. Safer to rewrite using parentheses:
```python
total = (1 +
         2 +
         3)
```

---

## ✍️ Code Completion Solutions

**1.**
```python
# this explains the next line
```

**2.**
```python
if age > 18:
    print("Adult")
```

**3.**
```python
total = (1 + 2 +
         3 + 4)
```

**4.**
```python
name1 = "invalid name example"
```
*(Any valid identifier not starting with a digit works — `name1` is just one example.)*

**5.**
```python
a = 1; b = 2; print(a + b)
```

---

## 🔮 Predict the Output — Answers

**1.**
```
A
B
C
```

**2.**
```
medium-or-big
done
```
*(x = 10, so `x > 5` is True and `x > 8` is True too, meaning "big" would ALSO print — let's re-derive: since x=10 > 8, "big" prints too.)*
Corrected output:
```
big
medium-or-big
done
```

**3.**
```
visible
```

**4.**
```
3
```

**5.**
```
6
```

---

## 🚀 Coding Challenge Solutions

**1.**
```python
score = 85

if score >= 90:
    print("Grade: A")
else:
    if score >= 80:
        print("Grade: B")
    else:
        if score >= 70:
            print("Grade: C")
        else:
            print("Grade: F")
```
**Output:** `Grade: B`

**2.**
```python
total = (10 + 20 +
         30 + 40 +
         50 + 60)
```

**3.**
```python
# This script calculates and displays a simple total.
price = 19.99
quantity = 3
total = price * quantity  # multiply unit price by quantity to get total cost
print(total)
# print("debug line disabled for now")
```

**4.**
```python
first_name = "Ada"
age = 28
is_student = False
gpa = 3.9
courses = ["Math", "CS", "Physics"]
```

**5.**
```python
# The following would raise an IndentationError because "print('b')" uses
# 2-space indentation while its sibling "print('a')" uses 4-space indentation
# within the same block.
if True:
    print("a")
  print("b")
```
