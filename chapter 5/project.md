# 🛠️ Mini Project: Student Information System (v1)

## Goal

Build a simple "Student Information System" that stores and updates student data using variables, practicing binding, reassignment, augmented assignment, and the reference-vs-copy distinction.

## Requirements

1. Store a student's name, age, GPA, and a list of enrolled courses using clearly named variables.
2. Use augmented assignment to simulate the GPA changing after a new grade is factored in.
3. Demonstrate the difference between an **alias** (`enrolled_courses_ref = enrolled_courses`) and an independent **copy** (`enrolled_courses_backup = enrolled_courses.copy()`).
4. Print a clean summary "report card" of the student's information at the end.

## Starter Code

```python
# ---- Student Information System (v1) ----

student_name = "Ada Lovelace"
student_age = 20
gpa = 3.5
enrolled_courses = ["Mathematics", "Computer Science"]

# Simulate a GPA bump after a strong semester using augmented assignment
gpa += 0.3

# Alias vs. copy demonstration
enrolled_courses_ref = enrolled_courses       # shares the SAME list
enrolled_courses_backup = enrolled_courses.copy()  # INDEPENDENT copy

# Student adds a new course this semester
enrolled_courses.append("Physics")

print("=" * 35)
print("STUDENT REPORT CARD")
print("=" * 35)
print(f"Name:              {student_name}")
print(f"Age:               {student_age}")
print(f"GPA:               {gpa:.2f}")
print(f"Current Courses:   {enrolled_courses}")
print(f"Alias Sees:        {enrolled_courses_ref}   (same list, so it updated too)")
print(f"Backup (Old) List: {enrolled_courses_backup}   (independent copy, unaffected)")
print("=" * 35)
```

**Expected Output:**
```
===================================
STUDENT REPORT CARD
===================================
Name:              Ada Lovelace
Age:               20
GPA:               3.80
Current Courses:   ['Mathematics', 'Computer Science', 'Physics']
Alias Sees:        ['Mathematics', 'Computer Science', 'Physics']   (same list, so it updated too)
Backup (Old) List: ['Mathematics', 'Computer Science']   (independent copy, unaffected)
===================================
```

## Stretch Goals (Optional)

- Add a second student using multiple assignment on one line (`name2, age2, gpa2 = ...`).
- Use the swap idiom to swap which of two students is considered "top of the class" based on GPA (just swap two variables holding their names).
- Add an `is` vs `==` check comparing `enrolled_courses` and `enrolled_courses_backup`, and print the result with a short explanation comment.

## What This Project Teaches

| Concept Practiced | Where it came from |
|---|---|
| Variable assignment & naming | Chapter 5 |
| Augmented assignment (`+=`) | Chapter 5 |
| Alias vs. independent copy | Chapter 5 |
| f-string formatting | Preview of Chapter 08 - Input/Output |
