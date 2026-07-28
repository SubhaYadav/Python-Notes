# 🏋️ Chapter 4 — Practice

> Attempt every question before checking [`solutions.md`](./solutions.md).

---

## 🟢 Beginner (10 Questions)

1. What symbol does Python use to define code blocks instead of curly braces?
2. What symbol marks the start of a single-line comment?
3. What punctuation mark must appear at the end of an `if`, `for`, or `def` line before its indented block?
4. True or False: Python is case-sensitive, so `age` and `Age` are different variables.
5. Can an identifier start with a number? (Yes/No)
6. Can you use the word `class` as a variable name? Why or why not?
7. How many spaces does PEP 8 recommend per indentation level?
8. Name one character used for explicit line continuation.
9. What error does Python 3 raise if you mix tabs and spaces inconsistently?
10. Is `a = 1; b = 2` legal Python? Is it recommended?

---

## 🟡 Intermediate (10 Questions)

1. Explain, in your own words, how Python decides where an indented block starts and ends.
2. What are `INDENT` and `DEDENT` tokens, conceptually?
3. Why does Python 3 raise a `TabError` when tabs and spaces are mixed inconsistently?
4. List three rules that a valid Python identifier must follow.
5. What is a "keyword" in Python, and why can't you reuse one as a variable name?
6. Show two different valid ways to continue a long expression across multiple lines.
7. Why does PEP 8 prefer parentheses-based line continuation over backslash continuation?
8. Why do comments have zero effect on program performance?
9. Give one example of a "bad" comment (one that adds no value) and explain why.
10. What's the difference between an inline comment and a full-line comment? Give an example of each.

---

## 🔴 Advanced (10 Questions)

1. Describe conceptually how Python's tokenizer transforms raw indentation whitespace into a stream of tokens the parser can use.
2. Why is Python's whitespace-based syntax considered controversial by some developers coming from brace-based languages, and what's the counterargument in its favor?
3. Construct an example where inconsistent indentation would cause a `IndentationError` versus one where it would cause logically different (but still valid) behavior — explain the difference between these two failure types.
4. Why does using semicolons to chain statements on one line make debugging tracebacks slightly harder, even though it's legal syntax?
5. What would happen if two sibling blocks (e.g., the `if` body and its matching `else` body) were indented at different widths (e.g., 4 spaces vs 8 spaces) — is this legal, and why or why not?
6. Explain why comments and whitespace are entirely absent from compiled bytecode, and what this implies about their runtime cost.
7. Why might a linter (a code-quality checking tool) flag both `tab-based indentation` and `overly long lines needing awkward continuation` as issues, from a team-collaboration perspective?
8. Compare Python's colon-plus-indentation block syntax to C's brace-based block syntax in terms of how each prevents (or fails to prevent) a specific category of real-world bugs (hint: think about the historic "goto fail" or dangling-else style bugs).
9. Why is `total = (1 + 2 +\n 3)` considered safer than a trailing-backslash version, specifically regarding trailing whitespace after the continuation character?
10. Explain why identifiers are case-sensitive in Python, and give a realistic scenario where this could cause a subtle bug for a beginner.

---

## 🐞 Debugging Problems (5)

**1.**
```python
if True
    print("yes")
```

**2.**
```python
def greet():
print("hi")
```

**3.**
```python
if True:
    print("a")
      print("b")
```

**4.**
```python
class = "Math101"
print(class)
```

**5.**
```python
total = 1 + \
    2 + 
    3
```
*(Hint: trailing whitespace/newline placement after the backslash matters.)*

---

## ✍️ Code Completion Problems (5)

**1.** Complete the line so this is a valid single-line comment.
```python
____ this explains the next line
```

**2.** Complete the `if` statement so it's syntactically valid.
```python
if age > 18____
    print("Adult")
```

**3.** Rewrite this backslash-continued line using parentheses instead.
```python
total = 1 + 2 + \
        3 + 4
```

**4.** Fix the identifier so it's valid (currently starts with a digit).
```python
____ = "invalid name example"
```

**5.** Complete the multi-statement line using the correct separator.
```python
a = 1____b = 2____print(a + b)
```

---

## 🔮 Predict the Output (5)

**1.**
```python
if True:
    print("A")
    print("B")
print("C")
```

**2.**
```python
x = 10
if x > 5:
    if x > 8:
        print("big")
    print("medium-or-big")
print("done")
```

**3.**
```python
# print("hidden")
print("visible")
```

**4.**
```python
a = 1; b = 2; print(a + b)
```

**5.**
```python
total = (1 +
         2 +
         3)
print(total)
```

---

## 🚀 Coding Challenges (5)

1. Write a nested `if/else` structure (3 levels deep) that correctly prints different messages based on a variable `score` (e.g., grade bands), using proper indentation throughout.
2. Rewrite a long addition expression of 6 numbers using parentheses-based line continuation across 3 lines.
3. Write a small script with at least 3 comments: one full-line comment explaining the script's purpose, one inline comment explaining a specific calculation, and one comment temporarily disabling a line of code.
4. Write 5 valid, well-named identifiers for variables that would store: a person's first name, their age, whether they're a student, their GPA, and a list of their courses (don't worry about the list syntax itself yet — just the variable name).
5. Deliberately write a small snippet with mixed 2-space and 4-space indentation between sibling lines inside the same block, then explain in a comment above it why it would fail.
