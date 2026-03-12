# ask-codex

A [Claude Code skill](https://docs.anthropic.com/en/docs/claude-code/skills) that gives you an independent second opinion on code, PR comments, technical decisions, or implementation plans.

Codex reads the actual source files, verifies claims against code, checks line references, and gives a clear VALID / PARTIALLY VALID / INVALID verdict for each item.

## Install

```bash
# Global (all projects)
cp -r ask-codex ~/.claude/skills/

# Per-project
cp -r ask-codex .claude/skills/
```

Or clone directly:

```bash
git clone https://github.com/lucas-domeij/ask-codex.git ~/.claude/skills/ask-codex
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
