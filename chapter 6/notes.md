# 🗒️ Chapter 6 — Quick Notes & Cheat Sheet

## Key Points

- Every object has an **identity**, a **type**, and a **value**.
- Core types: `int`, `float`, `complex`, `str`, `bool`, `list`, `tuple`, `dict`, `set`, `frozenset`, `NoneType`.
- **Mutable** (can change in place): `list`, `dict`, `set`.
- **Immutable** (cannot change in place): `int`, `float`, `complex`, `str`, `tuple`, `bool`, `frozenset`.
- Only **hashable** (generally, immutable) types can be dictionary keys or set elements.
- `int()`, `float()`, `str()`, `bool()` explicitly convert between types ("casting").
- `int()` **truncates** toward zero; it does not round. Use `round()` to round.
- Use `is None` / `is not None`, not `== None`.

## Cheat Sheet

| Type | Example | Mutable? |
|---|---|---|
| `int` | `42` | No |
| `float` | `3.14` | No |
| `complex` | `2 + 3j` | No |
| `str` | `"hello"` | No |
| `bool` | `True` / `False` | No |
| `list` | `[1, 2, 3]` | **Yes** |
| `tuple` | `(1, 2, 3)` | No |
| `dict` | `{"a": 1}` | **Yes** |
| `set` | `{1, 2, 3}` | **Yes** |
| `frozenset` | `frozenset({1,2})` | No |
| `NoneType` | `None` | N/A (singleton) |

## Common Mistakes

- Adding a string and an int directly (`"5" + 5`) without converting.
- Trying to use a list as a dictionary key (`TypeError: unhashable type`).
- Assuming `int(9.9)` rounds to `10` (it truncates to `9`).
- Using `== None` instead of `is None`.
- Assuming `bool("False")` is `False` — any non-empty string is truthy regardless of content.

## Frequently Asked Questions

**Q: Why does Python have both `list` and `tuple` if they're both ordered sequences?**
Because mutability matters: tuples signal "this data shouldn't change" and are hashable (usable as dict keys), while lists are for data you intend to modify.

**Q: Is `frozenset` commonly used?**
Less common than `set`, but it appears when you need a hashable, immutable collection of unique items — e.g., as a dictionary key or a set element.

**Q: What's the difference between `int()` and `round()`?**
`int()` always truncates toward zero regardless of the decimal part; `round()` rounds to the nearest whole number (or specified decimal place) using standard rounding rules.

## Interview Questions (Quick Recall)

1. What three things does every object have?
2. Name two mutable types and two immutable types.
3. Why can't a list be a dictionary key?
4. What does `int(9.9)` return?
5. What's the idiomatic way to check for `None`?

*(Full explained answers are in `README.md` and `quiz.md`.)*
