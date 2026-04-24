# Gemini Study Suite: Python & LeetCode Mastery

Elevate your technical interview game with specialized Gemini CLI Skills. This repository provides a suite of tools designed for job seekers and students to master idiomatic Python and build a comprehensive LeetCode study guide.

## 🚀 The Skills

### 1. Interview Prep: Python Enhancement
**Skill Name:** `interview-prep-enhance-python`

*   **What it does:** Acts as a senior engineer reviewer, transforming basic Python into professional, idiomatic (Pythonic) code following the **Google Python Style Guide**.
*   **Significance:** Most interviews at top-tier companies aren't just about solving the problem; they're about how you solve it. This skill ensures you use type hints, efficient literals, and clean docstrings, helping you clear the "professionalism" bar.
*   **Key Features:** Enforces `snake_case`, promotes `zip`/`enumerate`, and standardizes resource handling with `with` statements.

### 2. LeetCode Study Plan
**Skill Name:** `leetcode-study-plan`

*   **What it does:** Automatically processes LeetCode problems and solutions. It extracts constraints, validates Big-O complexity, identifies the "essence" of the problem, and explores alternative approaches.
*   **Significance:** Random practice is less effective than structured review. This skill automates the creation of a **Personal LeetCode Guide**, forcing you to think about space/time trade-offs and different algorithmic strategies (e.g., Two Pointers vs. Hash Map).
*   **Key Features:** Automated categorization (Arrays, Strings, DP, etc.), complexity verification, and standardized Markdown output.

---

## 🛠 Installation

You must have [Gemini CLI](https://github.com/google/gemini-cli) installed to use these skills.

### Option A: Install from `.skill` bundles (Recommended)
These are pre-packaged versions of the skills.
```bash
gemini skills install interview-prep-enhance-python.skill
gemini skills install leetcode-study-plan.skill
```

### Option B: Install from source directories
If you want to view or modify the skill logic:
```bash
gemini skills install interview-prep-enhance-python/
gemini skills install leetcode-study-plan/
```

### Option C: Link for active development
If you are contributing to this repo and want changes to reflect immediately:
```bash
gemini skills link .
```

---

## 💡 Usage

Gemini CLI will automatically activate these skills when it detects relevant prompts.

### Python Mastery
Ask Gemini for beginner tips or idiomatic refactors:
> *"How do I iterate over two lists at once in a Pythonic way?"*
> *"Refactor this dictionary loop to be more idiomatic."*

### LeetCode Archiving
Provide a LeetCode problem and your solution:
> *"I just solved LeetCode 1. Two Sum using a nested loop. Can you summarize this, verify the complexity, and show me the optimal Hash Map approach?"*

---

## 📂 Project Structure

- `interview-prep-enhance-python/`: Source for the Python enhancement skill.
- `leetcode-study-plan/`: Source for the LeetCode processor skill.
- `leetcode-guide/`: **Your Study Vault.** This directory is automatically populated by the `leetcode-study-plan` skill.
    - Organized by category (e.g., `arrays/`, `math/`, `strings/`).
    - Files are formatted as `[Number].[camelCaseName].md`.
    - Fully compatible with **Obsidian** or other Markdown-based knowledge bases.

---

## 📈 Significance for Your Career

In a competitive job market, consistency and quality are key.
- **Consistency:** Use the `leetcode-study-plan` to build a habit of documenting your learning.
- **Quality:** Use `interview-prep-enhance-python` to ensure your coding style matches industry leaders.

Happy Hacking! 🐍🔥
