# Abyssal Text Analyzer

This repository contains the Abyssal Text Analyzer, a Python program that analyzes two pieces of text to check for palindromes and anagram/window matches. The interactive script is available as `main.py` on the `rename-code-to-main` branch.

Changes in this branch:
- Added `main.py` containing the analyzer and interactive menu.
- Replaced older `code` file with a placeholder pointing to `main.py`.

How to run:
1. git fetch origin
2. git checkout rename-code-to-main
3. python main.py

Notes:
- The code uses `collections.Counter` and a sliding-window technique to detect anagram matches.
