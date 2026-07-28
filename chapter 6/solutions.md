# ✅ Chapter 6 — Solutions

---

## 🟢 Beginner Solutions

1. `type()`
2. `int`, `float`, `complex`
3. Immutable.
4. Mutable.
5. `True` and `False`.
6. The absence of a value / "nothing here yet."
7. `int()`
8. `str()`
9. **True**.
10. **False**.

---

## 🟡 Intermediate Solutions

1. Identity, type, and value.
2. `list`, `dict`, `set`.
3. `int`, `float`, `complex`, `str`, `tuple`, `bool`, `frozenset`.
4. A hashable type produces a stable, unchanging hash value over its lifetime; dictionaries rely on this to consistently locate keys. Mutable types can't guarantee a stable hash (since their contents can change), so they're disallowed as keys.
5. `int(9.9)` returns `9` (truncates toward zero); `round(9.9)` returns `10` (rounds to the nearest whole number).
6. Because `bool()` on a string only checks whether the string is **empty or non-empty** — any non-empty string, regardless of its actual text content (even `"False"`), is truthy.
7. `if value is None:` — preferred because `None` is a single, unique singleton object, so identity comparison is both correct and typically faster than a full equality check.
8. A tuple signals "this shouldn't change" and is more memory/performance efficient for genuinely fixed data; a list signals "this may be modified" and supports methods like `.append()`.
9. Example: `"5" + 5` raises `TypeError: can only concatenate str (not "int") to str`. Fix: `int("5") + 5` or `"5" + str(5)`.
10. `frozenset` is useful when you need a hashable, immutable set — for example, using a set of values as a dictionary key or as an element inside another set, neither of which a regular mutable `set` can do.

---

## 🔴 Advanced Solutions

1. Dictionary keys require a stable hash value computed from the key's contents. Lists are mutable, so their contents (and therefore their hash) could change after insertion, which would corrupt the dictionary's internal lookup structure — so Python disallows hashing lists entirely. Tuples containing only immutable elements are hashable because their contents (and thus their hash) can never change.
2. It raises `TypeError: unhashable type: 'list'` — even though the outer container is a tuple, Python must be able to hash *every* element to compute the tuple's overall hash, and a list inside it is still mutable and unhashable, so the whole tuple becomes unhashable too.
3. `x is None` is an identity check — essentially comparing memory addresses/pointers directly, which is a very cheap, constant-time operation. `x == None` is an equality check, which (in general) could invoke a custom `__eq__` method defined on `x`'s type, potentially doing more work than a simple identity comparison.
4. Because immutable objects can never be changed after creation, so passing one around (sharing a reference to it) carries no risk of one part of the program unexpectedly altering data that another part is relying on — every reference sees the same, permanently fixed value.
5. Because strings are immutable — `text + "!"` computes a brand-new string object containing the combined characters, and then `text = ...` simply rebinds the name `text` to point at that new object. The original string object is untouched (and unreferenced, if nothing else pointed to it).
6. Tuples are generally slightly more memory-efficient and faster to construct than lists of the same size, because CPython can apply certain internal optimizations for objects it knows will never change size or contents (e.g., simpler memory layout, no need to over-allocate space for potential future growth).
7. Example: `int("28.5")` raises `ValueError: invalid literal for int() with base 10: '28.5'`, because the string contains a decimal point that `int()` cannot directly parse — you'd need `int(float("28.5"))` if truncation to `28` was intended.
8. `bool(0)` is `False` because `0` is the numeric "falsy" value. `bool("0")` is `True` because it's a non-empty string — `bool()` on strings only checks emptiness, not numeric content, so the string `"0"` (which has length 1) is truthy despite "looking like zero."
9. `type(x) == int` fails to recognize subclasses of `int` as valid matches (it demands an *exact* type match), while `isinstance(x, int)` correctly recognizes both `int` itself and any subclass of it — making `isinstance()` more flexible and idiomatic for most type-checking needs (full inheritance context arrives in Chapter 16 - OOP).
10. `complex` numbers exist to represent numbers with a real and imaginary component (`a + bj`), which is essential for certain mathematical/engineering/signal-processing computations (like Fourier transforms or electrical engineering calculations), but simply irrelevant for the vast majority of everyday programming tasks that only deal with real numbers.

---

## 🐞 Debugging Solutions

**1.** `age` is a string; you can't `+` a string and an int directly.
```python
age = "28"
print(int(age) + 5)
```

**2.** Lists aren't hashable and can't be dictionary keys.
```python
cache = {}
key = (1, 2)   # use a tuple instead
cache[key] = "result"
```

**3.** `int()` truncates rather than rounds.
```python
value = 9.9
rounded = round(value)
print(rounded)  # 10
```

**4.** `bool("False")` is `True` because the string is non-empty — checking string *content* requires an explicit comparison, not relying on truthiness.
```python
flag = "False"
if flag == "True":
    print("This will correctly NOT run.")
```

**5.** Works correctly, but the more idiomatic version uses `is`:
```python
result = None
if result is None:
    print("No result yet")
```

---

## ✍️ Code Completion Solutions

**1.**
```python
text = "42"
number = int(text)
```

**2.**
```python
if x is None:
    print("x has no value")
```

**3.**
```python
value = 3.14
print(type(value))
```

**4.**
```python
key = (1, 2, 3)
cache = {key: "cached"}
```

**5.**
```python
count = 5
text = str(count)
```

---

## 🔮 Predict the Output — Answers

**1.**
```
<class 'int'>
<class 'float'>
<class 'str'>
```

**2.**
```
False
True
False
True
```

**3.**
```
<class 'tuple'>
```

**4.**
```
cats
cat
```
*(`a = a + "s"` creates a new string object; `b` still refers to the original `"cat"`.)*

**5.**
```
7
8
```

---

## 🚀 Coding Challenge Solutions

**1.**
```python
name = "Ada"
age = 28
height = 1.75
is_student = False
hobbies = ["reading", "coding"]

print(type(name))
print(type(age))
print(type(height))
print(type(is_student))
print(type(hobbies))
```
**Output:**
```
<class 'str'>
<class 'int'>
<class 'float'>
<class 'bool'>
<class 'list'>
```

**2.**
```python
user_input = "123"
result = int(user_input) + 7
print(result)
```
**Output:** `130`

**3.**
```python
valid_key = (1, 2, 3)
cache = {valid_key: "works!"}
print(cache)

try:
    invalid_key = [1, 2, 3]
    cache2 = {invalid_key: "won't work"}
except TypeError as e:
    print(f"Error: {e}")
```
**Output:**
```
{(1, 2, 3): 'works!'}
Error: unhashable type: 'list'
```

**4.**
```python
a = None
b = 0
c = ""

for label, value in [("a", a), ("b", b), ("c", c)]:
    if value is None:
        print(f"{label} is None (no value)")
    else:
        print(f"{label} is NOT None, it's: {value!r}")
```
**Output:**
```
a is None (no value)
b is NOT None, it's: 0
c is NOT None, it's: ''
```

**5.**
```python
for value in [4.4, 4.5, 4.6]:
    print(f"int({value}) = {int(value)}, round({value}) = {round(value)}")
```
**Output:**
```
int(4.4) = 4, round(4.4) = 4
int(4.5) = 4, round(4.5) = 4
int(4.6) = 4, round(4.6) = 5
```
*(Note: `round(4.5)` may surprise beginners — Python uses "round half to even" / banker's rounding for `.5` cases, which is explored further in Chapter 07 - Operators.)*
