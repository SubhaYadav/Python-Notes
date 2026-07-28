# 🧪 Chapter 5 — Quiz (20 Questions)

Try to answer all 20 before scrolling to the **Answers** section at the bottom.

1. Is a Python variable a container holding a value, or a name bound to an object?
2. What error occurs when you reference a variable that was never assigned?
3. What does `total += 10` mean?
4. What does the idiom `a, b = b, a` do?
5. What casing convention is standard for Python variable names?
6. What casing convention is used (by convention only) for constants?
7. Does Python enforce that `ALL_CAPS` names can't be reassigned?
8. True/False: A Python variable is locked to the type of its first assigned value forever.
9. What does `==` compare?
10. What does `is` compare?
11. If `b = a` and `a` is a list, does modifying `b` affect `a`?
12. How do you make an independent copy of a list `a`?
13. Why does `x = 5; y = 5; x is y` commonly return `True` in CPython?
14. Why might `x = 500; y = 500; x is y` return `False`?
15. What does Python build internally for `name, age = "Ada", 28`?
16. Why does the swap idiom work without a temporary variable?
17. Why is naming a variable `list` or `type` discouraged?
18. What happens in memory when you reassign a variable to a new value?
19. What is a namespace, conceptually?
20. Why does explicit copying matter more for mutable objects than immutable ones?

---

## ✅ Answers

1. A name bound to an object — the variable itself is a reference/label, not a container
2. `NameError`
3. Shorthand for `total = total + 10`
4. Swaps the values that `a` and `b` refer to
5. `snake_case`
6. `ALL_CAPS`
7. No — it's purely a human convention, not technically enforced
8. False — Python is dynamically typed, so a variable can be reassigned to a different type
9. Value equality
10. Object identity (whether two names reference the exact same object in memory)
11. Yes — because `b` and `a` reference the same underlying list object
12. `b = a.copy()` (or `b = list(a)`)
13. CPython caches small integers (-5 to 256) as shared objects, so both names point to the same cached object
14. Numbers outside the cached range are typically created as separate objects each time, so identity isn't guaranteed
15. A tuple, e.g. `("Ada", 28)`, which is then unpacked to bind each name
16. Because the entire right-hand side is evaluated into a temporary tuple before any left-hand name is reassigned
17. Because it shadows Python's built-in `list()`/`type()` functions, breaking any later code in that scope that tries to use them
18. The name is re-bound to point at a new (or reused/cached) object; the old object isn't modified, and becomes eligible for garbage collection if nothing else references it
19. A lookup table (conceptually like a dictionary) mapping names to the objects they currently reference
20. Because mutable objects can be changed in place, so a shared reference means changes via one name are visible via another — which is often unintended; immutable objects can't be changed in place, so sharing a reference carries no such risk
