---
name: ask-codex
description: Get an independent second opinion from OpenAI Codex CLI on code, PR comments, technical decisions, or implementation plans. Use when the user wants validation, a sanity check, or a critical review of their work.
argument-hint: "[file path, PR URL, code snippet, review comments, or technical question]"
---

# Ask Codex - Independent Validation via Codex CLI

Run the OpenAI Codex CLI to get a truly independent second opinion from a different model.

## Your task

Get Codex to validate and critique: $ARGUMENTS

## How to run

1. **Build the prompt** based on what needs reviewing. Include context about what to validate.
2. **Run Codex non-interactively** using `codex exec` with full permissions:

```bash
codex exec --dangerously-bypass-approvals-and-sandbox -m o3 -o /tmp/codex-output.md "YOUR PROMPT HERE"
```

### For validating PR comments or review notes:

```bash
codex exec --dangerously-bypass-approvals-and-sandbox -m o3 -o /tmp/codex-output.md "You are an independent code reviewer. Read the file FILEPATH and the source files it references. For each comment, verify the technical claims against the actual code - check line references, check assumptions, confirm behavior. Give a verdict for each: VALID, PARTIALLY VALID, or INVALID with a brief explanation. End with a summary table."
```

### For reviewing code changes:

```bash
codex exec --dangerously-bypass-approvals-and-sandbox -m o3 -o /tmp/codex-output.md "Review the current git diff. Check for bugs, edge cases, missed issues, and whether the code does what it claims. Be critical and specific."
```

### For validating technical decisions:

```bash
codex exec --dangerously-bypass-approvals-and-sandbox -m o3 -o /tmp/codex-output.md "Read FILEPATH and evaluate the technical approach. Is the reasoning sound? Are there better alternatives? What are the tradeoffs? What could go wrong?"
```

## Options

- Use `-m o3` for the strongest reasoning (default)
- Use `-m o4-mini` for faster responses
- Use `-o /tmp/codex-output.md` to save output to a file
- Always use `--dangerously-bypass-approvals-and-sandbox` so it runs without interruption

## After Codex responds

Read the output from `/tmp/codex-output.md` and summarize the findings for the user. If Codex found issues with PR comments or code, help the user decide what to fix, update, or drop.
