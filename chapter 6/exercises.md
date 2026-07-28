# 🏋️ Chapter 6 — Practice

> Attempt every question before checking [`solutions.md`](./solutions.md).

---

## 🟢 Beginner (10 Questions)

1. What function checks the type of a value in Python?
2. Name three numeric types in Python.
3. Is a `str` mutable or immutable?
4. Is a `list` mutable or immutable?
5. What are the two possible values of a `bool`?
6. What does `None` represent?
7. What function converts a value to an integer?
8. What function converts a value to a string?
9. True or False: A tuple can be used as a dictionary key.
10. True or False: A list can be used as a dictionary key.

---

## 🟡 Intermediate (10 Questions)

1. What three properties does every Python object have?
2. List all the mutable built-in types covered in this chapter.
3. List all the immutable built-in types covered in this chapter.
4. What does it mean for a type to be "hashable," and why does it matter for dictionary keys?
5. What does `int(9.9)` return, and how does that differ from `round(9.9)`?
6. Why is `bool("False")` equal to `True`?
7. What's the idiomatic way to check whether a variable is `None`, and why is it preferred over `== None`?
8. What's the practical difference between choosing a `tuple` vs. a `list` for a fixed set of coordinates?
9. Give an example of an implicit type mismatch error and how to fix it.
10. Why might a `frozenset` be useful, given that `set` already exists?

---

## 🔴 Advanced (10 Questions)

1. Explain, using the concept of hashing, exactly why lists cannot be dictionary keys but tuples (of immutable elements) can.
2. What happens if you attempt `{(1, [2,3]): "value"}` — a tuple containing a mutable list — as a dictionary key? Predict and explain.
3. Why is checking `x is None` generally faster than `x == None`, at the level of what each operation actually does internally?
4. Explain why immutable objects are considered "safer to share" across different parts of a program compared to mutable ones.
5. Why does `text = text + "!"` on a string not modify the original string object, even though it looks like an in-place update?
6. Compare the memory/performance implications of using a `list` vs. a `tuple` for a fixed-size collection that will never change.
7. Explain a realistic scenario where converting `int("28")` would raise a `ValueError`, and why.
8. Why does `bool()` behave differently for `0` vs `"0"` (as a string)? Predict the output of each and explain.
9. Why is `type(x) == int` generally considered less flexible than `isinstance(x, int)` (even though full coverage of `isinstance` and inheritance comes later, in Chapter 16 - OOP)?
10. Explain why `complex` numbers are rarely used outside specific scientific/engineering contexts, based on what kind of problems they're designed to solve.

---

## 🐞 Debugging Problems (5)

**1.**
```python
age = "28"
print(age + 5)
```

**2.**
```python
cache = {}
key = [1, 2]
cache[key] = "result"
```

**3.**
```python
value = 9.9
rounded = int(value)
print(rounded)  # Beginner expected 10
```

**4.**
```python
flag = "False"
if flag:
    print("This runs, but the beginner expected it not to.")
```

**5.**
```python
result = None
if result == None:
    print("No result yet")
# Works, but what's the more idiomatic version?
```

---

## ✍️ Code Completion Problems (5)

**1.** Complete the conversion so `"42"` becomes the integer `42`.
```python
text = "42"
number = ____(text)
```

**2.** Complete the check for whether `x` is `None`, using the idiomatic approach.
```python
if x ____ None:
    print("x has no value")
```

**3.** Complete the code to check a value's type.
```python
value = 3.14
print(____(value))
```

**4.** Complete the tuple so it could safely be used as a dictionary key.
```python
key = ____  # should be an immutable sequence of 1, 2, 3
cache = {key: "cached"}
```

**5.** Complete the conversion so the number `5` becomes the string `"5"`.
```python
count = 5
text = ____(count)
```

---

## 🔮 Predict the Output (5)

**1.**
```python
print(type(10))
print(type(10.0))
print(type("10"))
```

**2.**
```python
print(bool(0))
print(bool(1))
print(bool(""))
print(bool("hello"))
```

**3.**
```python
x = (1, 2, 3)
print(type(x))
```

**4.**
```python
a = "cat"
b = a
a = a + "s"
print(a)
print(b)
```

**5.**
```python
print(int(7.99))
print(round(7.99))
```

---

## 🚀 Coding Challenges (5)

1. Write code that stores a person's data using at least 5 different data types (int, float, str, bool, list) and prints each value's type using `type()`.
2. Write code that safely converts a user-entered string `"123"` to an integer, adds `7` to it, and prints the result.
3. Write code demonstrating that a tuple can be used as a dictionary key but a list cannot (using a `try/except` to catch the error gracefully).
4. Write code that checks whether a variable is `None` using the idiomatic approach, for three different variables (one that is `None`, one that is `0`, one that is `""`), printing an appropriate message for each.
5. Write code that demonstrates the difference between `int()` truncation and `round()` rounding for the values `4.4`, `4.5`, and `4.6`.
