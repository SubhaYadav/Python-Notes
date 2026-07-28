# 🛠️ Mini Project: Syntax-Clean Receipt Printer

## Goal

Practice correct indentation, comments, identifiers, and line continuation by building a small script that prints a formatted store receipt.

## Requirements

1. Use properly named identifiers (no single letters except loop counters, which you haven't learned yet — that's fine, skip loops for now).
2. Include at least 3 comments: a purpose comment, an inline comment, and a "disabled code" comment.
3. Use nested `if` statements (at least 2 levels) to apply a discount based on total price, with correct, consistent indentation.
4. Use parentheses-based line continuation for at least one long expression.

## Starter Code

```python
# ---- Store Receipt Printer ----
# This script calculates a total price and applies a tiered discount.

item_price = 45.50
quantity = 3
tax_rate = 0.08  # 8% sales tax

subtotal = item_price * quantity

total_with_tax = (subtotal +
                   (subtotal * tax_rate))

if total_with_tax >= 100:
    if total_with_tax >= 150:
        discount = 0.15
    else:
        discount = 0.10
else:
    discount = 0.0

final_total = total_with_tax * (1 - discount)

print("=" * 30)
print("RECEIPT")
print("=" * 30)
print(f"Subtotal:        ${subtotal:.2f}")
print(f"Total with tax:  ${total_with_tax:.2f}")
print(f"Discount:        {discount * 100:.0f}%")
print(f"Final total:     ${final_total:.2f}")
print("=" * 30)

# print("DEBUG: raw discount value =", discount)
```

**Expected Output (with the given values):**
```
==============================
RECEIPT
==============================
Subtotal:        $136.50
Total with tax:  $147.42
Discount:        10%
Final total:     $132.68
==============================
```

## Stretch Goals (Optional)

- Add a third discount tier for totals over $200 (25% off).
- Rewrite the nested `if` using `elif` once you've previewed Chapter 09 - Conditional Statements (optional preview — full coverage comes later).
- Deliberately break the indentation on one line, run the script, and read the exact error Python gives you.

## What This Project Teaches

| Concept Practiced | Where it came from |
|---|---|
| Consistent indentation across nested blocks | Chapter 4 |
| Comments (full-line, inline, disabled code) | Chapter 4 |
| Parentheses-based line continuation | Chapter 4 |
| Descriptive identifier naming | Chapter 4 |
| f-strings with formatting | Preview of Chapter 08 - Input/Output |
