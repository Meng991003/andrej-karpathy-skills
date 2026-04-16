# Copilot Workspace Instructions

Apply these rules for all coding tasks in this repository.

## Mandatory Pre-Edit Workflow

Before making any code or file edits:
1. Restate the requested change in one short sentence.
2. Run a short Karpathy checklist:
- Think Before Coding: list assumptions and ambiguities.
- Hard gate for ambiguity: if assumptions or ambiguities exist, ask for clarification using an interactive prompt (for example via vscode_askQuestions), then stop and wait for user input.
- While gated: do not continue to Simplicity First, Surgical Changes, or Goal-Driven Execution, and do not include edit plans or Step 2-4 content.
- Simplicity First: choose the minimum viable change.
- Surgical Changes: identify exactly which files/lines should change.
- Goal-Driven Execution: define how success will be verified.
3. Ask for explicit confirmation before applying any edits.

## Editing Rules

- Do not modify files until user confirmation is received.
- Keep diffs minimal and directly tied to the request.
- Do not refactor unrelated code.
- Preserve existing style and structure unless change is required.
- Mention unrelated issues, but do not change them unless asked.

## Verification Rules

- Validate changes with tests/lint/build when available and relevant.
- Report what was verified and what was not verified.

## Skill Reading Process

Skill-loading gate:
- Only read/load coding skills when the task requires code or file modifications.
- If the user is only asking questions, requesting explanation, or asking for read-only checks/research, do not load the coding skill.
- In read-only cases, proceed directly with analysis and mention that skill loading was skipped because no code change is required.

When a task may involve skills, follow this sequence:
1. Discover candidate skills from provided skill metadata (name, description, triggers).
2. Decide whether a skill is relevant to the current request before loading it.
3. Read the selected skill file(s) fully before implementation.
4. Summarize to the user what skill was loaded and why in 1-2 sentences.
5. Apply the skill guidance while still prioritizing explicit user instructions.

User-facing process update requirement:
- Before major edits, briefly state whether a skill was loaded, which skill, and what guidance is being applied.

Example scenarios:
- "Explain why this bug happens" -> Skip skill loading (read-only analysis).
- "Check whether this API is used anywhere" -> Skip skill loading (read/search only).
- "Fix this bug in the code" -> Load relevant coding skill before implementation.
- "Refactor this function for clarity" -> Load relevant coding skill before implementation.
