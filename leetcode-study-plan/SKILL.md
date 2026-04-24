---
name: leetcode-study-plan
description: Process LeetCode problems and solutions. Summarizes the problem, constraints, and examples. Provides a brief essence, high-level solution summary with Big-O, 1-2 alternative approaches, and saves the result to a categorized directory at /Users/clarencenguyen/projects/study/leetcode-guide/.
---

# LeetCode Study Plan

Use this skill when the user provides a LeetCode problem and solution to be stored and summarized.

## Workflow

1.  **Analyze Input**: Extract problem number, name, difficulty (Easy, Medium, Hard), description, constraints, examples, and the code.
2.  **Categorize**: Identify the problem type (e.g., Arrays, Graphs, DP, etc.).
3.  **Validate Big-O**: Critically analyze the provided solution's time and space complexity. If the user's provided Big-O notation is incorrect or suboptimal, identify the true complexity and use the correct one in the final output.
4.  **Generate Summary**:
    *   **Title**: Format as `[Problem Number]. [Problem Name] [[DIFFICULTY]]`.
    *   **What the problem is asking**
    *   **Constraints of the problem**
    *   **Examples**
    *   **Essence**: Summarize the problem's core in as few words as possible. Avoid paragraphs; make it scan-friendly.
    *   **High-level Summary**: Use bullet points for the main solution and 1-2 alternative approaches. Include **verified** Big-O time and space complexities for each.
    *   **Actual Code**: Include the provided solution first, then provide clean, idiomatic code for the alternative approaches discussed in the summary.
5.  **Save**: Write the output to `/Users/clarencenguyen/projects/study/leetcode-guide/<problem-type>/<number>.<name>.md`.
    *   The file name should be `<number>.<camelCaseName>.md` (e.g., `121.bestTimeToBuyAndSellStock.md`).

## Coding Standards
*   **Idiomatic Python**: Use list comprehensions, `map`, `zip`, `enumerate`, and proper slicing where appropriate.
*   **Type Hinting**: Include type hints for function parameters and return types (e.g., `List[int]`, `Optional[int]`).
*   **Readability**: Use descriptive variable names and ensure logical flow. Use `Solution` class structure common to LeetCode.

## Output Format Template

# [Number]. [Problem Name] [[DIFFICULTY]]

## What the problem is asking
[Brief description]

## Constraints
[Constraints]

## Examples
[Examples]

## Essence
[Extremely brief summary of the core objective]

## Solutions & Complexity
*   **Primary Approach: [Name]**
    *   [Brief bullet point description]
    *   **Time:** O(N)
    *   **Space:** O(1)
*   **Alternative Approach: [Name]**
    *   [Brief bullet point description]
    *   **Time:** O(N log N)
    *   **Space:** O(N)

## Code
### Provided Solution
```python
[Actual Code]
```

### Alternative: [Approach Name]
```python
[Idiomatic Alternative Code]
```
