# 🛠️ Mini Project: Universal Type Inspector

## Goal

Build a small tool that takes a handful of sample values, reports each one's type, whether it's mutable, and whether it could be safely used as a dictionary key — reinforcing the core distinctions from this chapter.

## Requirements

1. Store at least 8 sample values covering: `int`, `float`, `str`, `bool`, `list`, `tuple`, `dict`, `set`, and `None`.
2. For each value, print its type using `type()`.
3. For each value, attempt to use it as a dictionary key inside a `try/except` block, reporting success or failure.
4. Summarize which values are mutable vs. immutable based on what you observed.

## Starter Code

```python
# ---- Universal Type Inspector ----

samples = [
    42,
    3.14,
    "hello",
    True,
    [1, 2, 3],
    (1, 2, 3),
    {"a": 1},
    {1, 2, 3},
    None,
]

print("=" * 60)
print(f"{'VALUE':<20}{'TYPE':<15}{'USABLE AS DICT KEY?'}")
print("=" * 60)

for value in samples:
    value_type = type(value).__name__

    try:
        test_dict = {value: "test"}
        usable_as_key = "Yes"
    except TypeError:
        usable_as_key = "No (unhashable)"

    print(f"{str(value):<20}{value_type:<15}{usable_as_key}")

print("=" * 60)
```

**Expected Output:**
```
============================================================
VALUE               TYPE           USABLE AS DICT KEY?
============================================================
42                  int            Yes
3.14                float          Yes
hello               str            Yes
True                bool           Yes
[1, 2, 3]           list           No (unhashable)
(1, 2, 3)           tuple          Yes
{'a': 1}            dict           No (unhashable)
{1, 2, 3}           set            No (unhashable)
None                NoneType       Yes
============================================================
```

## Stretch Goals (Optional)

- Add `frozenset({1, 2, 3})` and `2 + 3j` (complex) to the samples list and predict their results before running.
- Extend the tool to also print `id(value)` for each item, and discuss (in a comment) why small cached integers might share IDs across separate runs.
- Add a summary line at the end counting how many samples were mutable vs. immutable, based on the "usable as dict key" results.

## What This Project Teaches

| Concept Practiced | Where it came from |
|---|---|
| Checking types with `type()` | Chapter 6 |
| Mutable vs. immutable / hashability | Chapter 6 |
| `try/except` for graceful error handling | Preview of Chapter 17 - Exception Handling |
| f-string formatting with alignment (`:<20`) | Preview of Chapter 08 - Input/Output |
