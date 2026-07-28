# 🧪 Chapter 4 — Quiz (20 Questions)

Try to answer all 20 before scrolling to the **Answers** section at the bottom.

1. What does Python use instead of curly braces to define code blocks?
2. What symbol starts a comment?
3. What punctuation must end an `if`/`for`/`def`/`class` line before its block?
4. Is Python case-sensitive?
5. Can an identifier start with a digit?
6. What are reserved words like `if`, `for`, and `class` called?
7. How many spaces does PEP 8 recommend per indentation level?
8. Name the two main ways to continue a long line of code.
9. What error does Python 3 raise when tabs and spaces are mixed inconsistently?
10. Is using semicolons to put multiple statements on one line legal?
11. Is it recommended by PEP 8?
12. What internal tokens does the tokenizer generate to mark block boundaries?
13. What happens to comments during compilation to bytecode?
14. Do comments affect runtime performance?
15. What's a "bad" comment, generally speaking?
16. What's the difference between an inline comment and a full-line comment?
17. What kind of error occurs when sibling lines in the same block have inconsistent indentation widths?
18. Why is a stray trailing space after a backslash continuation dangerous?
19. Why does Python's block syntax help prevent certain "looks right but isn't" bugs common in brace-based languages?
20. Give one example of an invalid Python identifier and explain why it's invalid.

---

## ✅ Answers

1. Indentation (whitespace)
2. `#`
3. A colon `:`
4. Yes
5. No
6. Keywords
7. 4 spaces
8. Parentheses/brackets-based continuation (preferred) and backslash `\` continuation (less preferred)
9. `TabError`
10. Yes, it's legal
11. No, PEP 8 recommends one statement per line
12. `INDENT` and `DEDENT`
13. They are stripped out entirely and never appear in the resulting bytecode
14. No — they have zero runtime cost
15. A comment that merely restates what the code obviously already shows, adding no new information
16. An inline comment shares a line with code (`x = 5  # note`); a full-line comment occupies its own line (`# note`)
17. `IndentationError`
18. It silently breaks the continuation (since the backslash must be the very last character on the line), often producing a confusing error far from the real mistake
19. Because Python's actual block structure IS the indentation — there's no way for code to visually look like it belongs to one block while actually belonging to another, unlike brace-based languages where indentation is just a style convention separate from the real (brace-defined) structure
20. Example: `2fast` — invalid because identifiers cannot start with a digit (any other valid example, like `class` for being a reserved keyword, is also acceptable)
