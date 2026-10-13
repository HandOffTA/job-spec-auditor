# job-spec-auditor

A Claude Skill that audits a job spec, scores it out of 100, names the specific clauses killing the funnel, reads the talent-pool constraint, and rewrites the spec ready to post.

## What it does

Most job specs are written as an internal wish list and never pressure-tested against the real talent market. This skill does that test and hands back something usable:

- **Scores out of 100** across six weighted dimensions, with sub-scores and reasons — not just a headline number
- **Names the spec killers** — the specific lines that shrink the funnel, quoted, with the mechanism of harm and the fix
- **Reads the talent pool** by layering the constraint stack (scarcest skill → geography → work model → comp) and naming the single relaxation that buys back the most pipeline
- **Rewrites the spec** in full, ready to post, with clearly marked brackets where a fact is genuinely unknown

## The rubric

| Dimension | Points |
|---|---|
| Role clarity and outcomes | 20 |
| Requirements realism | 20 |
| Talent pool viability | 20 |
| Comp and leveling coherence | 15 |
| Candidate appeal and differentiation | 15 |
| Inclusive and accessible language | 10 |

It scores honestly. A well-reasoned 62 is more useful than a generous 85, and the skill is written to defend a low score rather than inflate it when pushed.

## Install

**In Claude (web or desktop):**
1. Download `SKILL.md` from this repo, or zip the whole folder.
2. Open Claude's **Settings**.
3. Find the **Skills** section (under Capabilities).
4. Choose **Upload skill** and select the file.
5. The skill is now available in any chat.

**In Claude Code:**
1. Open a terminal.
2. Run `mkdir -p ~/.claude/skills/job-spec-auditor`
3. Copy `SKILL.md` into that folder.
4. Restart Claude Code. The skill loads automatically.

## How to use it

Paste or upload a job spec and ask in plain language. All of these trigger it:

- "Can you audit this JD before I post it?"
- "Why aren't we getting applicants for this role?"
- "Is this role actually fillable in Sacramento at that band?"
- "Score this spec and tell me what to fix."

It will ask once for location, work model, comp band, and company context if they aren't in the spec — then audit what it has and flag the rest as unknowns.

## What you get back

```
## Score: NN/100 — one-line verdict
### Breakdown            (table of sub-scores)
### Top spec killers     (quoted line → why it costs pipeline → the fix)
### Talent pool read     (constraint stack, verdict, highest-leverage relaxation)
### Questions for the hiring manager
### Rewritten spec       (full, ready to post)
```

## Notes

- It will not invent candidate counts or market comp figures. With web search available it verifies and cites; without it, estimates are stated as directional.
- It calibrates by market — skilled trades specs are judged on pay rate, shift, licensure, and drive time; startup tech specs on scope, stage, and equity clarity.

## Contents

```
job-spec-auditor/
├── SKILL.md     the skill itself
└── README.md    this file
```

## License

MIT
