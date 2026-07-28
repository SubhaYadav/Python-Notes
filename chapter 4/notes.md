# 🗒️ Chapter 4 — Quick Notes & Cheat Sheet

## Key Points

- Python uses **indentation** (not braces) to define code blocks — this is enforced syntax, not just style.
- A **colon `:`** marks the start of an indented block, after `if`, `elif`, `else`, `for`, `while`, `def`, `class`, `try`, `except`, `with`, etc.
- **Identifiers** (names) can use letters, digits, and underscores, but can't start with a digit and can't be a reserved keyword.
- Python is **case-sensitive**: `age` and `Age` are different names.
- **Comments** start with `#` and are ignored at runtime — they exist purely for humans.
- Long lines can continue using **parentheses/brackets** (preferred) or a trailing **backslash `\`** (less preferred).
- Mixing tabs and spaces in Python 3 raises a **`TabError`**.
- Multiple statements on one line via `;` are legal but discouraged by PEP 8.

## Cheat Sheet

| Rule | Example |
|---|---|
| Block start | `if x > 0:` then indent the next lines |
| Comment | `# explanation` |
| Valid identifier | `user_age`, `_private`, `age2` |
| Invalid identifier | `2fast`, `class` (reserved keyword) |
| Parentheses continuation | `total = (1 + 2 +\n         3)` |
| Backslash continuation | `total = 1 + 2 + \\\n        3` |
| Multiple statements (discouraged) | `a = 1; b = 2` |

## Common Mistakes

- Forgetting the trailing colon `:` before an indented block.
- Mixing indentation widths between sibling lines.
- Mixing tabs and spaces.
- Using a reserved keyword (like `class` or `for`) as a variable name.
- Starting a variable name with a digit.

## Frequently Asked Questions

**Q: How many spaces should I use per indentation level?**
PEP 8 recommends **4 spaces**. Stick to this consistently throughout a project.

**Q: Can I mix 2-space and 4-space indentation in the same file?**
Technically each block just needs internal consistency, but mixing widths across a file is a strong readability anti-pattern — always pick one width (4 spaces) project-wide.

**Q: Are semicolons ever necessary in Python?**
Rarely — mainly to put multiple simple statements on one line (discouraged) or occasionally in tools/generated code. Standard style is one statement per line, no semicolon needed.

## Interview Questions (Quick Recall)

1. How does Python define code blocks?
2. What happens if you mix tabs and spaces?
3. Can a keyword be used as a variable name?
4. Name two ways to continue a long statement across lines.
5. Why does PEP 8 discourage semicolon-separated statements?

*(Full explained answers are in `README.md` and `quiz.md`.)*
