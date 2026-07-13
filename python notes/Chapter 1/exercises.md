# 🏋️ Chapter 1 — Practice

> Attempt every question before checking [`solutions.md`](./solutions.md).

---

## 🟢 Beginner (10 Questions)

1. In one sentence, what is Python?
2. Who created Python, and in what year was it first released?
3. Is Python named after the snake or something else? What?
4. What does "high-level language" mean?
5. What symbol starts a comment in Python?
6. What function is used to display text on the screen?
7. True or False: Python code must end each line with a semicolon.
8. What is the default, most widely-used implementation of Python called?
9. What command do you type in a Python shell to see Python's design philosophy?
10. Name two fields Python is commonly used in.

---

## 🟡 Intermediate (10 Questions)

1. Explain the difference between source code, bytecode, and machine code.
2. What is the Python Virtual Machine (PVM), and what role does it play?
3. Explain why `id(x)` and `id(y)` might return the same value for `x = 10` and `y = 10`.
4. Name two implementations of Python other than CPython, and one property of each.
5. What is PEP 8, and why does it matter?
6. Why is Python described as trading performance for developer productivity?
7. What does it mean to say "everything in Python is an object"?
8. What's the difference between what `print()` does and what `return` does?
9. Give one example of a task where you would NOT recommend using Python.
10. What is the GIL, and which chapter will explore it in depth?

---

## 🔴 Advanced (10 Questions)

1. Explain, step by step, what happens between running `python3 script.py` and seeing output on your screen.
2. Why does CPython cache small integers, and what could go wrong if you relied on this caching behavior for equality checks using `is` instead of `==`?
3. Compare compiled languages (like C) and interpreted languages (like Python) in terms of execution speed and development speed. Give one real scenario where each trade-off wins.
4. What does a Just-In-Time (JIT) compiler (like the one PyPy uses) do differently from CPython's approach?
5. Why might a data science team choose Python even though it's slower than C, for numerically heavy workloads?
6. What is a `.pyc` file, and when does Python generate one?
7. Explain why the GIL affects multi-threaded CPU-bound programs but has less impact on I/O-bound programs.
8. In the advanced example using `@dataclass`, what would happen if `User` didn't use a dataclass and you tried the same list comprehension — what extra code would you need to write manually?
9. Why is Python considered "batteries included"? Give two examples of standard library modules that support this claim (you don't need to know their exact contents yet — a guess based on the term is fine at this stage).
10. What's one criticism of interpreted languages regarding error discovery timing, compared to statically-typed compiled languages?

---

## 🐞 Debugging Problems (5)

For each snippet, identify the bug and explain why it fails.

**1.**
```python
if age > 18
    print("Adult")
```

**2.**
```python
Print("Hello")
```

**3.**
```python
def greet(name):
print(f"Hi {name}")
```

**4.**
```python
name = "Ada"
    age = 28
```

**5.**
```python
x = 5
y = 10
if x = y:
    print("Equal")
```

---

## ✍️ Code Completion Problems (5)

**1.** Complete the function so it returns `True` if a number is even.
```python
def is_even(n):
    # your code here
```

**2.** Complete the f-string so it prints `"Age next year: 29"` when `age = 28`.
```python
age = 28
print(f"Age next year: {____}")
```

**3.** Complete the loop to print each name in the list, one per line.
```python
names = ["Ada", "Grace", "Alan"]
for ____ in ____:
    print(____)
```

**4.** Complete the comment so this line is ignored by Python.
```python
____ this entire line should be ignored
```

**5.** Complete the code to check Python's version from the terminal (not inside a script).
```bash
python3 ____
```

---

## 🔮 Predict the Output (5)

**1.**
```python
print("Hello" + " " + "World")
```

**2.**
```python
x = 10
y = 10
print(x is y)
```

**3.**
```python
def greet(name):
    return f"Hi {name}"

result = greet("Sam")
print(result)
```

**4.**
```python
print(type(10))
print(type("10"))
```

**5.**
```python
temps = [22, 31, 28, 35]
hot = [t for t in temps if t >= 30]
print(hot)
```

---

## 🚀 Coding Challenges (5)

1. Write a program that prints your name, age, and favorite programming language on three separate lines using a single `print()` call with `\n`.
2. Write a program that stores three city temperatures in a list and prints the average.
3. Write a function `is_python3()` (conceptually — no need to actually check system version yet) that returns a string explaining why explicitly typing `python3` matters.
4. Using an f-string, write a program that prints "In 5 years, I will be X years old" based on a variable `current_age`.
5. Write a one-line list comprehension that filters a list of numbers to keep only values greater than 100.
