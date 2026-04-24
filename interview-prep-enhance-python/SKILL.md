---
name: interview-prep-enhance-python
description: Use when asking about study tips and beginner questions about Python.
---

# Interview Prep: Python Enhancement

## Overview
Brief, idiomatic Python answers following Google Coding Style. Focuses on Pythonic patterns and interview-readiness.

## When to Use
- Beginner Python questions (e.g., "how to make a dictionary").
- Interview prep or study tip requests.
- Idiomatic (Pythonic) code requests.

## Core Guidelines (Google Style)
- **Naming**: `snake_case` (vars/funcs), `PascalCase` (classes).
- **Docs**: Use Google-style docstrings for all functions.
- **Idioms**:
  - **Prefer Literals**: `[]`, `{}`, `()` over `list()`, `dict()`, `tuple()`.
  - **Comprehensions**: Use list/dict/set comprehensions for simple transformations.
  - **Iteration**: Use `enumerate()` for index+value, `zip()` for parallel items.
  - **Context**: Always use `with` for file/resource handling.
  - **Types**: Use type hints for clarity.

## Idiomatic Examples

### 1. Dictionary & List Creation
```python
def get_user_data(names: list[str], ages: list[int]) -> dict[str, int]:
    """Maps names to ages using a dictionary comprehension.

    Args:
        names: List of user names.
        ages: List of user ages.

    Returns:
        A dictionary mapping name to age.
    """
    # Idiomatic: zip for parallel lists and dict comprehension
    return {name: age for name, age in zip(names, ages)}
```

### 2. Enumeration
```python
def print_top_items(items: list[str]):
    """Prints items with their rank (1-indexed)."""
    # Idiomatic: enumerate(items, start=1) instead of range(len(items))
    for rank, item in enumerate(items, start=1):
        print(f"{rank}. {item}")
```

### 3. Handling Missing Keys
```python
from collections import defaultdict

def count_occurrences(items: list[str]) -> dict[str, int]:
    """Counts item occurrences using defaultdict."""
    # Idiomatic: defaultdict handles missing keys automatically
    counts = defaultdict(int)
    for item in items:
        counts[item] += 1
    return dict(counts)
```

## Quick Reference
| Feature | Legacy/Non-Idiomatic | Idiomatic (Pythonic) |
|---------|----------------------|-----------------------|
| Loops with Index | `for i in range(len(l)):` | `for i, val in enumerate(l):` |
| Parallel Lists | `for i in range(len(a)): ... b[i]` | `for x, y in zip(a, b):` |
| Key Check | `if key in d: d[key] += 1` | `d[key] = d.get(key, 0) + 1` |
| String Formatting | `"%s %s" % (a, b)` | `f"{a} {b}"` |
