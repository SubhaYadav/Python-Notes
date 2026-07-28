# 🗒️ Chapter 5 — Quick Notes & Cheat Sheet

## Key Points

- A variable is a **name bound to an object** — not a box holding a value directly.
- Assignment (`=`) binds a name to an object; it doesn't necessarily create a new object.
- Python is **dynamically typed** — the same name can point to different types over time.
- `b = a` for a mutable object (list, dict, set) makes `b` and `a` reference the **same** object — no copy is made.
- `==` compares **values**; `is` compares **identity** (same object in memory).
- Multiple assignment: `x = y = z = 0` or `name, age = "Ada", 28`.
- Augmented assignment: `score += 5` is shorthand for `score = score + 5`.
- Swap idiom: `a, b = b, a` works because the right-hand tuple is built before any rebinding happens.
- Naming: `snake_case` for variables, `ALL_CAPS` for constants (by convention only — not enforced).

## Cheat Sheet

| Syntax | Meaning |
|---|---|
| `x = 5` | Bind name `x` to the int object `5` |
| `x = y = 0` | Bind both `x` and `y` to the same object `0` |
| `a, b = 1, 2` | Bind `a` to `1` and `b` to `2` |
| `a, b = b, a` | Swap what `a` and `b` point to |
| `score += 5` | `score = score + 5` |
| `MAX_USERS = 100` | Convention for a constant |
| `a is b` | True if `a` and `b` are the same object |
| `a == b` | True if `a` and `b` have equal values |

## Common Mistakes

- Using a variable before it's assigned (`NameError`).
- Assuming `b = a` copies a mutable object — it doesn't.
- Confusing `=` (assignment) with `==` (comparison).
- Shadowing built-in names like `list`, `type`, `str` as variable names.

## Frequently Asked Questions

**Q: Does Python enforce that `ALL_CAPS` names can't be changed?**
No — it's purely a human convention. Python has no true "constant" keyword; `ALL_CAPS` just signals intent to other developers.

**Q: Why does `a is b` sometimes return `True` for small integers even without explicit sharing?**
CPython caches small integers (-5 to 256) as shared objects for performance, so two separate assignments of the same small integer may coincidentally point to the same cached object.

**Q: How do I actually copy a list instead of just referencing it?**
Use `b = a.copy()` or `b = list(a)` — covered in more depth in Chapter 13 - Arrays.

## Interview Questions (Quick Recall)

1. Is a variable a box or a label?
2. What does "dynamically typed" mean?
3. Difference between `is` and `==`?
4. Does `b = a` copy a list?
5. What naming convention is used for constants?

*(Full explained answers are in `README.md` and `quiz.md`.)*
