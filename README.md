# Gemini Study Suite: Professional Interview Preparation

A collection of specialized Gemini CLI skills to standardize Python implementations and automate LeetCode study workflows.

## Core Features & Benefits

### Python Code Enhancement (`interview-prep-enhance-python`)
- **Description:** An automated reviewer that aligns Python code with the **Google Python Style Guide**.
- **Focus:** Enforces idiomatic practices (type hints, docstrings, `zip`/`enumerate`, context managers).
- **Value:** Ensures code meets industry standards for readability and maintainability.

### LeetCode Study Automation (`leetcode-study-plan`)
- **Description:** A tool for generating structured documentation from LeetCode problem-solving sessions.
- **Focus:** Extracts constraints, verifies Big-O complexity, and documents alternative strategies.
- **Value:** Automates a categorized study repository for efficient review of algorithmic patterns.

## Installation & Setup

### Prerequisites
Requires [Gemini CLI](https://github.com/google/gemini-cli).

### Installation
- **Pre-packaged:** `gemini skills install [name].skill`
- **From source:** `gemini skills install [directory]/`
- **Active development:** `gemini skills link .`

## Usage & Project Organization

### Usage Examples
- **Python Refactors:** Ask Gemini for idiomatic refactors (e.g., dictionary loops, list iteration).
- **LeetCode Summaries:** Provide a problem and solution for complexity verification and optimal approach exploration.

### Project Structure
- `interview-prep-enhance-python/`: Python enhancement skill source.
- `leetcode-study-plan/`: LeetCode study plan skill source.
- `leetcode-guide/`: Automated repository of solved problems, organized by category (Arrays, Strings, etc.), compatible with **Obsidian**.
