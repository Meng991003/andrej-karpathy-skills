---
name: karpathy-guidelines
description: 'Behavioral guidelines for coding tasks. Use when implementing, reviewing, refactoring, or debugging code to avoid hidden assumptions, overengineering, broad side effects, and weak success criteria.'
argument-hint: 'Optional: describe your task type (implement, bugfix, refactor, review)'
user-invocable: true
---

# Karpathy Guidelines

A focused workflow to reduce common LLM coding mistakes, adapted for GitHub Copilot Chat skill loading.

## When to Use
- Implementing new features where scope can drift
- Fixing bugs where assumptions can hide root causes
- Refactoring where over-abstraction is a risk
- Code review where minimal, targeted diffs matter

## Procedure
1. Think Before Coding
- State assumptions explicitly.
- If requirements are ambiguous or assumptions are needed, present interpretations and assumptions first, then invoke an interactive clarification prompt (for example via vscode_askQuestions) to collect user input or confirmation.
- Hard gate: after triggering clarification, stop the workflow and do not continue to Simplicity First, Surgical Changes, or Goal-Driven Execution until the user responds.
- Output rule while gated: end the response with clarification questions or options only; do not include an edit plan or any Step 2-4 content.
- Surface tradeoffs and call out the simplest viable approach.

2. Simplicity First
- Solve only what was requested.
- Avoid speculative abstractions and premature flexibility.
- Prefer minimal code that is easy to verify.

3. Surgical Changes
- Touch only files and lines required by the request.
- Preserve existing style and structure unless change is required.
- Clean up only artifacts introduced by your own edit.

4. Goal-Driven Execution
- Convert requests into verifiable outcomes.
- For bug fixes, reproduce first when feasible.
- Validate with tests, lint, or direct checks before finalizing.

## Success Signals
- Diffs are narrow and directly tied to the ask.
- Fewer rewrites due to overcomplication.
- Clarifications happen before implementation.
- Verification evidence is included in the result.

## Tradeoff
This workflow favors correctness and clarity over speed for non-trivial tasks. For obvious one-line changes, apply proportionate effort.
