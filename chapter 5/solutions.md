# ✅ Chapter 5 — Solutions

---

## 🟢 Beginner Solutions

1. `age = 30`
2. A sticky-note label pointing at a box — the variable is a reference, not the value's actual container.
3. `NameError`
4. `=`
5. `total += 10`
6. It swaps the values `a` and `b` refer to — after running, `a` holds what `b` used to hold, and vice versa.
7. `snake_case` (lowercase with underscores).
8. `ALL_CAPS` (all uppercase with underscores).
9. **False** — Python is dynamically typed; a variable can be reassigned to a different type at any time.
10. `==`

---

## 🟡 Intermediate Solutions

1. Name binding means associating a name (like `age`) with an object living somewhere in memory, recorded in the current namespace — the name is essentially a pointer/reference to that object, not a container holding the value itself.
2. Python creates (or reuses, for cached small integers) a new `20` object, then updates `score`'s entry in the namespace to point at that new object instead of the old `10` object. The old `10` object is left with no reference from `score` anymore (it may still be referenced elsewhere, or become eligible for garbage collection if not).
3. `==` compares values; `is` compares identity (same object in memory). Example: `a = [1, 2]; b = [1, 2]; print(a == b)` → `True` (equal values), but `print(a is b)` → `False` (two separate list objects).
4. Yes, `a` changes too — because `b = a` makes `b` reference the exact same list object as `a`; there is only one list in memory, and both names point to it.
5. Use `b = a.copy()` (or `b = list(a)`), which creates a new, independent list object with the same contents.
6. Dynamic typing means a variable's type is determined by whatever object it currently references, and can change freely over the variable's lifetime. Static typing (as in Java/C) locks a variable to one declared type permanently, checked at compile time.
7. Python builds a tuple `("Ada", 28)` on the right-hand side first, then unpacks it, binding `name` to the first element and `age` to the second.
8. Because the entire right-hand side (`b, a`) is evaluated into a temporary tuple *before* any assignment to the left-hand names happens — so the "old" values of both `a` and `b` are captured together before either name is overwritten.
9. Because `list` and `type` are also the names of Python's built-in list-constructor and type-inspection functions; reassigning them as variables "shadows" (hides) the built-in, breaking any code later in that scope that tries to actually use `list()` or `type()` as functions.
10. Because integer caching (-5 to 256) is a CPython **implementation detail**, not a language guarantee — numbers outside that range are not guaranteed to be cached, so `is` comparisons on numbers can give inconsistent, implementation-dependent results; `==` is the correct, portable way to compare values.

---

## 🔴 Advanced Solutions

1.
```
a ---> [1, 2]  (list object #1)
b ---> [1, 2]  (same object #1, since b = a)
c ---> [1, 2]  (list object #2, separate from #1, since c was created fresh)
```
`a` and `b` share one object; `c` is a distinct object that happens to hold equal values.
2. Reassignment simply changes which object a name points to — it never mutates the previously-referenced object. CPython tracks, for each object, how many names/references currently point to it (its "reference count"). When a name is reassigned away from an object and that object's reference count drops to zero (no other names or containers reference it), it becomes eligible for garbage collection and its memory can be reclaimed.
3. CPython caches small integers in the range -5 to 256 as shared, reused objects — so `x = 5; y = 5` both end up pointing at the *same* cached `5` object, making `x is y` `True`. Integers outside that cached range (like `500`) are typically created as fresh, separate objects each time, so `x is y` may be `False` even though `x == y` is `True`. This is a CPython implementation detail, not guaranteed language behavior.
4. Python evaluates the entire right-hand side `b, a` into a temporary tuple **before** performing any assignment. So even though the first name (`a`) gets reassigned "first" from a left-to-right reading perspective, the values it's being reassigned *from* were already captured together in that temporary tuple, so nothing is lost.
5. Static typing lets tools (compilers, IDEs) catch type-mismatch errors *before* the program ever runs, at the cost of more upfront ceremony (explicit type declarations). Dynamic typing lets you write and iterate faster with less ceremony, but certain type-related bugs (like calling a string method on what turns out to be an integer) may only surface at runtime, when that specific line executes.
6. Example: a beginner writes `original_list = [1, 2, 3]`, then `backup = original_list` intending `backup` to be a "snapshot" they can compare against later. They then modify `original_list` (e.g., `original_list.append(4)`), and are surprised `backup` also shows `[1, 2, 3, 4]` — because `backup` was never an independent copy, just another name for the same list. Fix: use `backup = original_list.copy()`.
7. The "box" metaphor implies the variable itself directly contains and stores the value, and that assigning `b = a` would copy the contents into a new box — which is exactly backwards for Python's actual model, where the variable is a reference/label, and `b = a` makes two labels point at the *same* box, not two separate boxes with identical contents.
8. It would not raise any error — Python has no true constant-enforcement mechanism. `MAX_USERS = 200` simply rebinds the name to a new object, just like any other reassignment; `ALL_CAPS` is purely a human convention signaling "please treat this as unchanging," not a technical restriction.
9. A namespace is essentially a dictionary mapping names (as strings) to the objects they currently reference. Every variable assignment is really an operation that adds or updates an entry in the relevant namespace (e.g., a function's local namespace, or the module's global namespace) — covered in full in Chapter 12 - Scope.
10. Because immutable objects (ints, strings, tuples) can never be changed in place — so even if two names reference the "same" immutable object, there's no risk of one name's later modifications unexpectedly affecting the other. Mutable objects (lists, dicts, sets) CAN be changed in place, so a shared reference means changes via one name are visible via the other, which is often unintended — making explicit copying important specifically for mutable types.

---

## 🐞 Debugging Solutions

**1.** `score` is referenced before it's assigned.
```python
score = 10
print(score)
```

**2.** This is not a bug in the code — it's a bug in the beginner's mental model. `b = a` makes `b` and `a` reference the same list, so `b.append(4)` correctly also affects what `a` sees. If an independent copy was intended:
```python
a = [1, 2, 3]
b = a.copy()
b.append(4)
print(a)  # [1, 2, 3] — unaffected now
```

**3.** `=` is assignment, not comparison; use `==`.
```python
if age == 18:
    print("Exactly 18")
```

**4.** `type` was reassigned as a string, shadowing the built-in `type()` function, so calling it as a function fails.
```python
vehicle_type = "SUV"
print(type("hello"))  # now refers to the built-in function again
```

**5.** Too many values to unpack — the right side has 3 items but only 2 names on the left.
```python
x, y, z = 1, 2, 3
```

---

## ✍️ Code Completion Solutions

**1.**
```python
total = 10
total += 5
```

**2.**
```python
a, b = 1, 2
a, b = b, a
```

**3.**
```python
a = [1, 2, 3]
b = a.copy()
```

**4.**
```python
a = [1, 2]
b = a
print(a is b)
```

**5.**
```python
x = y = z = 0
```

---

## 🔮 Predict the Output — Answers

**1.**
```
<class 'str'>
```

**2.**
```
True
False
True
```

**3.**
```
13
```

**4.**
```
2 1
```

**5.**
```
[1, 2, 3]
```
*(`x` and `y` both point to the same list, so appending via `x` is visible through `y` too.)*

---

## 🚀 Coding Challenge Solutions

**1.**
```python
name, age, city = "Ada", 28, "London"
print(name, age, city)
```
**Output:** `Ada 28 London`

**2.**
```python
value = 42
print(type(value))
value = "forty-two"
print(type(value))
value = [42]
print(type(value))
```
**Output:**
```
<class 'int'>
<class 'str'>
<class 'list'>
```

**3.**
```python
original = [1, 2, 3]
alias = original
copy_of_original = original.copy()

original.append(4)

print("original:", original)
print("alias:", alias)
print("copy_of_original:", copy_of_original)
```
**Output:**
```
original: [1, 2, 3, 4]
alias: [1, 2, 3, 4]
copy_of_original: [1, 2, 3]
```

**4.**
```python
balance = 1000
balance += 500   # deposit
balance -= 200   # withdrawal
balance *= 1.02  # 2% interest applied
print(round(balance, 2))
```
**Output:** `1326.0`

**5.**
```python
first = "Alice"
second = "Bob"
print("Before:", first, second)
first, second = second, first
print("After:", first, second)
```
**Output:**
```
Before: Alice Bob
After: Bob Alice
```
