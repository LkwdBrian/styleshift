# CLAUDE.md — StyleShift

Guidance for Claude Code when working in this repo.

## What this repo is

StyleShift is a collection of Claude skills that switch a conversation into a named creative writing style via slash command (`/yoda`, `/sonnet`, `/hemingway`, etc.). Each mode is a `SKILL.md` file with precise structural rules, not just tone guidance. Built and maintained by Brian Cosgrove / So Wired Productions.

Current version: v1.1.0 (per user memory; verify against latest tag before bumping).

## Repo structure

```
styleshift/
  README.md          — mode table, install instructions, general rules (source of truth for the mode list)
  SKILL.md            — all nine modes bundled in a single file (Option 1 install)
  LICENSE
  modes/
    yoda/SKILL.md
    sonnet/SKILL.md
    play/SKILL.md
    seuss/SKILL.md
    haiku/SKILL.md
    limerick/SKILL.md
    epic/SKILL.md
    noir/SKILL.md
    hemingway/SKILL.md
  .github/            — workflows/config, check before assuming empty
```

Two install paths exist side by side: the bundled root `SKILL.md` and the per-mode files under `modes/`. **Any edit to a mode's rules must be made in both places** — the root file and its corresponding `modes/<name>/SKILL.md` — or the two install options will drift out of sync. This is the single most important repo-specific rule.

## General rules all modes must follow

From README.md, these apply to every mode and should be checked when editing or adding one:

1. Stay in mode until the user types `/normal`
2. Never break character to add prose clarifications — encode all information in the form itself
3. Accuracy is non-negotiable — style must never sacrifice correctness
4. Acknowledge activation, always confirm a mode switch in the activated style
5. Unknown mode names — respond with the mode list and ask the user to pick

## Common tasks

**Add a new mode:**
1. Create `modes/<name>/SKILL.md` with the mode's structural rules (meter, rhyme scheme, POV constraints, etc., not just adjectives)
2. Add the same mode content into the bundled root `SKILL.md`
3. Add a row to the mode table in `README.md` (mode name, slash command, one-line description)
4. Add the mode folder link to the "Individual mode files" list in `README.md`

**Edit an existing mode's rules:**
1. Edit `modes/<name>/SKILL.md`
2. Make the matching edit in the root `SKILL.md`
3. No README change needed unless the one-line description changes

**Release a new version:**
1. Confirm all mode files and the bundled file are in sync first
2. Tag the release (check existing tag pattern with `git tag -l` before choosing the next one)
3. Update the version reference in README.md if one exists there

## Working conventions

- Prefer `gh` CLI for routine repo operations in this session (status checks, PR creation, tag/release management) since it's faster and lighter than going through conversational GitHub tool calls for things with a known, fixed syntax
- Use GitHub MCP tools instead when the task is exploratory (e.g. "what changed across all modes since last release," cross-file search) rather than a single fixed command
- No build step, no dependencies, no CI pipeline currently in `.github/` unless discovered otherwise, check before assuming

## Style rules for any prose Claude writes in this repo (README, commit messages, docs)

- No em dashes or double hyphens mid-sentence
- Arial/grayscale/docx conventions from Brian's other work do not apply here, this is a public GitHub repo in Markdown
- Avoid: delve, straightforward, nuanced, groundbreaking, transformative, game-changing, leverage (verb), seamlessly, robust, comprehensive, "it's worth noting," "at the end of the day," "in conclusion," "to summarize," "of course," "it's important to note"
