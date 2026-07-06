---
name: oj-submit-workflow
description: Solve and submit online judge programming practice problems from a browser page using a local C++ workspace. Use when the user asks Codex to complete coding exercises already open in Chrome or another browser, write or replace main.cpp, choose C++ in the submission form, upload the file, submit, wait or navigate between problems, and continue problem-by-problem.
---

# OJ Submit Workflow

## Core Workflow

1. Read the current problem from the browser page. Prefer the accessibility tree or copied page text over screenshots when the page is small or blurry.
2. Identify the input format, output format, constraints, samples, and any platform-specific wording such as whether blank output is required when no answer exists.
3. Edit the local `main.cpp` only, unless the user specifies another file.
4. Use C++ in a compact algorithm-contest style:
   - no comments unless the user asks
   - no unnecessary abstractions
   - short variable names
   - no AI-flavored explanation in code
   - standard headers that compile locally when possible
5. Compile and run the sample locally before submitting.
6. In the browser submission area:
   - choose `C++` in the programming language dropdown
   - choose the current `main.cpp`
   - click submit
7. Watch the judge result. If it is not accepted, diagnose from the problem statement and visible result, patch `main.cpp`, rerun the sample, and resubmit.
8. After an accepted submission, follow the user’s requested pacing before moving to the next problem. If the user says to continue immediately, skip the remaining wait.
9. Navigate to the next problem using the page’s top or bottom navigation and repeat.

## Browser Handling

Use Computer Use or browser tooling to operate the live page when the user asks for real submission. The initial user request to submit solutions counts as approval for selecting the source file and clicking the platform’s submit button.

When extracting a problem statement:

- Use the browser accessibility tree if it exposes the statement and form controls.
- If text is hard to read, select/copy the page or use available browser inspection tools.
- Record enough details to avoid solving a nearby but different classic version of the problem.

## Local Coding Loop

Before editing, inspect the existing `main.cpp` if it exists. Replace it for the current problem unless the user asks to preserve prior code.

Use `apply_patch` for manual edits. Compile with a local command such as:

```bash
g++ -std=c++17 -O2 -Wall -Wextra main.cpp -o main
```

Run the sample exactly as shown. If the local compiler does not support a non-standard header, switch to standard includes instead of assuming the judge will accept it.

## Judge Result Loop

Treat partial scores as actionable:

- Wrong answer on a hidden case usually means a statement detail differs from a familiar original problem.
- Re-read the exact output requirements before changing the algorithm.
- Re-submit only after local compile succeeds.

When the result is accepted, note the score and then continue according to the user’s pacing instruction.

## Safety Notes

Do not solve CAPTCHAs, bypass browser security warnings, change account settings, or perform unrelated site actions. If a login or permission prompt appears and the user has not clearly approved it, ask before proceeding.
