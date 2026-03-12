# ask-codex

A [Claude Code skill](https://docs.anthropic.com/en/docs/claude-code/skills) that runs the [OpenAI Codex CLI](https://github.com/openai/codex) to get an independent second opinion on code, PR comments, technical decisions, or implementation plans.

Uses a completely different model (o3) as the reviewer, so you get a genuinely independent perspective - no self-preference bias.

## Prerequisites

- [Codex CLI](https://github.com/openai/codex) installed and authenticated
- OpenAI API key configured

## Install

```bash
# Global (all projects)
git clone https://github.com/lucas-domeij/ask-codex.git ~/.claude/skills/ask-codex

# Per-project
git clone https://github.com/lucas-domeij/ask-codex.git .claude/skills/ask-codex
```

## Usage

```
/ask-codex reviews/pr-comments.md
/ask-codex is my caching approach in app/services/foo.rb sound?
/ask-codex https://github.com/org/repo/pull/123
```

## What it validates

- **PR comments/reviews** - Are technical claims accurate? Line refs correct? Worth posting?
- **Code changes** - Bugs, edge cases, issues the author missed?
- **Technical decisions** - Reasoning sound? Better alternatives?
- **Implementation plans** - Feasible? What could go wrong?

## License

MIT
