# Design Spec: README Rewrite for Gemini Study Suite

**Date:** 2026-04-23
**Topic:** Professionalize README and remove "AI-sounding" tone.
**Approach:** Option 1 - "Tools for Success" (Product-Focused & Clear).

## 1. Introduction & Purpose
**Goal:** Define the project clearly for Python developers preparing for technical interviews.
- **Header:** `Gemini Study Suite: Professional Interview Preparation`
- **Content:** A collection of specialized Gemini CLI skills to standardize Python implementations and automate LeetCode study workflows.

## 2. Core Features & Benefits
**Goal:** Detail the technical functionality and professional value of the two primary skills.

### Python Code Enhancement (`interview-prep-enhance-python`)
- **Description:** An automated reviewer that aligns Python code with the **Google Python Style Guide**.
- **Focus:** Enforces idiomatic practices (type hints, docstrings, `zip`/`enumerate`, context managers).
- **Value:** Ensures code meets industry standards for readability and maintainability.

### LeetCode Study Automation (`leetcode-study-plan`)
- **Description:** A tool for generating structured documentation from LeetCode problem-solving sessions.
- **Focus:** Extracts constraints, verifies Big-O complexity, and documents alternative strategies.
- **Value:** Automates a categorized study repository for efficient review of algorithmic patterns.

## 3. Installation & Setup
**Goal:** Direct and instructional setup steps.
- **Prerequisites:** Requires [Gemini CLI](https://github.com/google/gemini-cli).
- **Installation:**
  - Pre-packaged: `gemini skills install [name].skill`
  - From source: `gemini skills install [directory]/`
  - Active development: `gemini skills link .`

## 4. Usage & Project Organization
**Goal:** Show workflow examples and repository structure.
- **Usage Examples:**
  - Python refactors (e.g., dictionary loops, list iteration).
  - LeetCode summaries (e.g., complexity verification, optimal approach exploration).
- **Project Structure:**
  - `interview-prep-enhance-python/`: Python enhancement skill source.
  - `leetcode-study-plan/`: LeetCode study plan skill source.
  - `leetcode-guide/`: Automated repository of solved problems, organized by category (Arrays, Strings, etc.), compatible with **Obsidian**.

## 5. Success Criteria
- No emojis or "AI-sounding" hyperbolic language.
- Professional, human-sounding, and product-focused tone.
- Clear, value-driven descriptions of all features and workflows.
