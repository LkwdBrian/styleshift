# StyleShift — Creative Writing Modes for Claude

A collection of Claude skills that switch conversations into named creative writing styles. Each mode has precise structural rules — not just tone guidance — so outputs are consistently well-formed and useful, not just vaguely stylistic.

Built and maintained by [Brian Cosgrove](https://sowired.info) / So Wired Productions.

---

## How It Works

Drop a skill file into your Claude skills directory and activate it with a slash command. Modes stay active for the remainder of a conversation until you type `/normal`.

---

## Available Modes

| Mode | Command | Description |
|---|---|---|
| **Yoda** | `/yoda` | Yoda's inverted OSV syntax, wisdom-forward, sparse. The user is "the Padawan," Claude is "Master Claude." |
| **Sonnet** | `/sonnet` | Every response as a Shakespearean sonnet — ABAB CDCD EFEF GG, iambic pentameter, closing couplet |
| **Play** | `/play` | Shakespearean drama format — iambic pentameter, stage directions, character voices, soliloquies |
| **Seuss** | `/seuss` | Dr. Seuss style — anapestic tetrameter, invented nouns, absurdist logic, earnest moral payoff |
| **Haiku** | `/haiku` | Every response as a haiku sequence — 5-7-5, kigo, juxtaposition, narrative arc |
| **Limerick** | `/limerick` | Every response as one or more limericks — AABBA, anapestic, punchline required |
| **Epic** | `/epic` | Homeric epic style — dactylic hexameter, epithets, Muse invocation, epic similes |
| **Noir** | `/noir` | Hard-boiled detective narration — cynical first person, simile-heavy, fatalistic, everything is a case |

---

## Installation

### Option 1: All Modes (Single File)

The fastest way to get everything. One file, all eight modes.

1. Download [`SKILL.md`](./SKILL.md) from the root of this repo
2. Place it in your Claude skills directory as `styleshift/SKILL.md`
3. All mode commands become available immediately

```
skills/
  styleshift/
    SKILL.md
```

### Option 2: Individual Modes

Install only the modes you want. Each lives in its own folder under `modes/`.

1. Navigate to the mode folder (e.g. `modes/yoda/`)
2. Download that `SKILL.md`
3. Place it in a named folder in your Claude skills directory

```
skills/
  styleshift-yoda/
    SKILL.md
  styleshift-noir/
    SKILL.md
```

Individual mode files: [`modes/yoda`](./modes/yoda/) · [`modes/sonnet`](./modes/sonnet/) · [`modes/play`](./modes/play/) · [`modes/seuss`](./modes/seuss/) · [`modes/haiku`](./modes/haiku/) · [`modes/limerick`](./modes/limerick/) · [`modes/epic`](./modes/epic/) · [`modes/noir`](./modes/noir/)

---

## General Rules (All Modes)

Every StyleShift mode follows these shared principles:

1. **Stay in mode** until the user types `/normal`
2. **Never break character** to add prose clarifications — encode all information in the form
3. **Accuracy is non-negotiable** — style must not sacrifice correctness
4. **Acknowledge activation** — always confirm a mode switch in the activated style
5. **Unknown mode names** — respond with the mode list and ask the user to pick

---

## About

StyleShift started as a personal productivity experiment — making Claude more interesting to interact with for creative and casual tasks, while keeping the outputs accurate and useful.

More skills and tools at [sowired.info](https://sowired.info).
