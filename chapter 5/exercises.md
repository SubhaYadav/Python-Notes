# 🏋️ Chapter 5 — Practice

> Attempt every question before checking [`solutions.md`](./solutions.md).

---

## 🟢 Beginner (10 Questions)

1. Write a line of code that assigns the value `30` to a variable named `age`.
2. Is a Python variable more like a labeled box, or a sticky-note label pointing at a box?
3. What error occurs if you try to print a variable that was never assigned?
4. What operator is used to reassign a variable's value?
5. Write the augmented assignment shorthand for `total = total + 10`.
6. What does the swap idiom `a, b = b, a` do?
7. What naming convention (casing style) is standard for Python variables?
8. What naming convention (casing style) is standard for constants?
9. True or False: In Python, a variable is permanently locked to the data type of its first assigned value.
10. What operator compares two variables' *values* for equality?

---

## 🟡 Intermediate (10 Questions)

1. Explain, in your own words, what "name binding" means.
2. What actually happens in memory when you write `score = 20` after `score` previously held `10`?
3. What's the difference between `==` and `is`? Give an example where they'd produce different results.
4. If `b = a` and `a` is a list, and you do `b.append(5)`, does `a` change too? Why?
5. How would you make `b` an independent copy of list `a`, instead of a shared reference?
6. What is dynamic typing, and how does it differ from static typing?
7. What does Python build internally when you write `name, age = "Ada", 28`?
8. Why does the swap idiom `a, b = b, a` work correctly without needing a temporary third variable?
9. Why is it considered bad practice to name a variable `list` or `type`?
10. Explain why CPython's integer caching (-5 to 256) means you should never rely on `is` for comparing numbers.

---

## 🔴 Advanced (10 Questions)

1. Draw (in words or ASCII) the memory diagram for: `a = [1, 2]`, `b = a`, `c = [1, 2]` — showing which names point to which objects.
2. Explain why reassigning a variable to a new value doesn't modify the old object, using the concept of reference counting/garbage collection at a conceptual level.
3. Why does `x = 5; y = 5; print(x is y)` commonly print `True`, but `x = 500; y = 500; print(x is y)` might print `False` on some systems? What CPython-specific behavior explains this?
4. Explain, step by step, why `a, b = b, a` produces a correct swap even though intuitively you might expect the first assignment to "overwrite" a value needed by the second.
5. Why does dynamic typing increase developer flexibility but potentially reduce a tool's ability to catch certain bugs before runtime, compared to statically typed languages?
6. Construct a realistic beginner bug scenario involving `b = a` on a mutable list, where the beginner did NOT intend for both variables to be linked, and explain the fix.
7. Why is it misleading to describe Python variables using the "box" metaphor common in introductory C or Java tutorials?
8. What would `MAX_USERS = 100` followed later by `MAX_USERS = 200` actually do in Python — would it raise an error, and why or why not?
9. Explain the relationship between a namespace (a name-to-object lookup table) and variable assignment.
10. Why does explicit copying (`.copy()`) matter more for mutable objects (lists, dicts) than for immutable ones (ints, strings, tuples)?

---

## 🐞 Debugging Problems (5)

**1.**
```python
print(score)
score = 10
```

**2.**
```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)  # Beginner expected this to print [1, 2, 3], unchanged
```

**3.**
```python
if age = 18:
    print("Exactly 18")
```

**4.**
```python
type = "SUV"
print(type("hello"))
```

**5.**
```python
x, y = 1, 2, 3
```

---

## ✍️ Code Completion Problems (5)

**1.** Complete the augmented assignment to add 5 to `total`.
```python
total = 10
total ____ 5
```

**2.** Complete the swap so `a` and `b` exchange values.
```python
a, b = 1, 2
a, b = ____, ____
```

**3.** Complete the code to make `b` an independent copy of list `a` (not a shared reference).
```python
a = [1, 2, 3]
b = a.____()
```

**4.** Complete the comparison to check whether two variables point to the *same object*.
```python
a = [1, 2]
b = a
print(a ____ b)
```

**5.** Complete the multiple assignment so `x`, `y`, and `z` all point to `0`.
```python
x = ____ = ____ = 0
```

---

## 🔮 Predict the Output (5)

**1.**
```python
x = 5
x = "five"
print(type(x))
```

**2.**
```python
a = [1, 2]
b = a
c = [1, 2]
print(a == c)
print(a is c)
print(a is b)
```

**3.**
```python
total = 10
total += 5
total -= 2
print(total)
```

**4.**
```python
a, b = 1, 2
a, b = b, a
print(a, b)
```

**5.**
```python
x = y = [1, 2]
x.append(3)
print(y)
```

---

## 🚀 Coding Challenges (5)

1. Write code that assigns three different variables (`name`, `age`, `city`) in a single line using multiple assignment, then prints all three using one `print()` call.
2. Write code demonstrating that reassigning a variable to a completely different type is legal (assign an int, then a string, then a list to the same variable name, printing the type each time).
3. Write code that creates a list `original`, creates `alias = original` (shared reference) and `copy_of_original = original.copy()` (independent copy), modifies `original`, and prints all three to demonstrate the difference.
4. Write a small program using augmented assignment (`+=`, `-=`, `*=`) to simulate a simple bank balance going through a deposit, a withdrawal, and interest being applied.
5. Write code that demonstrates the swap idiom `a, b = b, a` working correctly on two string variables, printing before and after values.
