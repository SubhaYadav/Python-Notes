# 🧪 Chapter 6 — Quiz (20 Questions)

Try to answer all 20 before scrolling to the **Answers** section at the bottom.

1. What function reveals a value's data type?
2. Name Python's three numeric types.
3. Is `str` mutable or immutable?
4. Is `list` mutable or immutable?
5. Is `tuple` mutable or immutable?
6. Is `dict` mutable or immutable?
7. What are the two values a `bool` can hold?
8. What does `None` represent?
9. What are the three properties every object has?
10. What does it mean for a type to be "hashable"?
11. Why can't a list be a dictionary key?
12. Can a tuple always be used as a dictionary key? Why or why not?
13. What does `int(9.9)` return?
14. What does `round(9.9)` return?
15. Why is `bool("False")` equal to `True`?
16. What's the idiomatic way to check if a variable is `None`?
17. Why is `is None` generally faster than `== None`?
18. What kind of numbers does `complex` represent?
19. What's the practical difference between choosing `tuple` over `list` for fixed data?
20. Why is `isinstance(x, int)` generally more flexible than `type(x) == int`?

---

## ✅ Answers

1. `type()`
2. `int`, `float`, `complex`
3. Immutable
4. Mutable
5. Immutable
6. Mutable
7. `True` and `False`
8. The absence of a value
9. Identity, type, and value
10. It produces a stable, unchanging hash value over its lifetime
11. Because lists are mutable, so their hash could change, which would corrupt a dictionary's internal lookup structure
12. Only if all of its elements are themselves hashable/immutable — a tuple containing a mutable list, for example, is not hashable
13. `9` (truncates toward zero)
14. `10` (rounds to nearest whole number)
15. Because `bool()` on a string only checks emptiness, not content — any non-empty string is truthy
16. `if value is None:`
17. Because identity comparison is a simple pointer check, while equality comparison could invoke a custom `__eq__` method
18. Numbers with a real and imaginary component (`a + bj`), used in scientific/engineering computation
19. Tuples signal fixed, unchanging data and are hashable (usable as dict keys); lists signal mutable data and support in-place modification methods
20. Because `isinstance()` also recognizes subclasses of the given type, while `type(x) ==` demands an exact type match
