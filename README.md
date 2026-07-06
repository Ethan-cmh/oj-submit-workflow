# oj-submit-workflow

A Codex skill for solving and submitting browser-based online judge practice problems with a local C++ workspace.

## What It Does

- Reads the current problem statement from the browser page.
- Writes or replaces `main.cpp` in the local workspace.
- Compiles and runs samples locally before submission.
- Selects C++ in the judge form, uploads `main.cpp`, and submits it.
- Watches judge results, diagnoses failures, patches the code, and resubmits when needed.
- Moves through consecutive problems when requested.

## Install

Copy the skill folder into your Codex skills directory:

```bash
cp -R oj-submit-workflow ~/.codex/skills/
```

Then invoke it from Codex with:

```text
$oj-submit-workflow
```

## Usage Example

```text
Use $oj-submit-workflow to finish problems 15-20.
```

## Responsible Use

This skill automates a workflow that can submit code to third-party online judge systems. Use it only where automation is allowed, and follow the rules of your course, contest, employer, or platform.

The skill does not solve CAPTCHAs, bypass browser security warnings, change account settings, or perform unrelated site actions.
