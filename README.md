# Case Agent

**A records-investigation toolkit for newsrooms that use AI coding agents.**
Built by a team at Arizona State University. ·
**Site:** https://ewyloge-asu.github.io/case-agent-for-newsrooms/

Case Agent lets an AI agent do the slow parts of a records investigation — loading
messy public records, connecting name variants to real people and companies, finding
outliers, tracking leads across weeks of sessions, checking claims against the actual
law, and footnoting a draft to primary sources — while keeping every number traceable
to the record it came from.

**One boundary is built in: the agent does not write the story.** It does the records
work and hands your reporter material they can verify. News judgment, framing, and the
writing stay with people. (Our view of where that line sits, and why, is in
[docs/editorial-standards.md](docs/editorial-standards.md).)

## Is this for you?

You'll get value from Case Agent if:

- your newsroom already uses (or is piloting) a code-executing AI agent — Claude Code,
  Cursor, or Cowork;
- you work with bulk public records: disclosures, filings, spending data, inspection
  reports, court data;
- you need the output to survive an editor, a fact-checker, and a lawyer.

You don't need a data team. You do need one person comfortable installing software and
setting an environment variable, and an org-level decision about cloud AI usage
([docs/data-and-source-protection.md](docs/data-and-source-protection.md) — read this
one first if you handle sensitive material).

## What's in the box

Six [Agent Skills](https://agentskills.io) that work alone or as one pipeline:

| Skill | What it does for you |
|---|---|
| `investigative-method` | Interviews the reporter to scope the investigation, then drives the rest; includes tools that find public datasets and APIs for any topic |
| `lobbying-influence-mapper` | The analysis engine, configured for money-in-politics records; the pattern generalizes to other beats |
| `robodoig` | Hand it any CSV/Excel file, get a full profile: what's in it, what's normal, what correlates |
| `case-file` | The investigation's memory across sessions: leads, statuses, entities, journal — plain text files your whole desk can read |
| `checking-the-law` | Reads the actual statute and applies it element by element; built to under-claim |
| `howard-center-footnoter` | Footnotes a draft to primary sources as Word tracked changes; flags unsupported claims instead of papering over them |

Install and first run: **[docs/getting-started.md](docs/getting-started.md)** —
15 minutes to a first result on bundled demo data, then your own records.

## The documentation

| Doc | Read it when |
|---|---|
| [Getting started](docs/getting-started.md) | You're installing it |
| [Editorial standards](docs/editorial-standards.md) | Your editor asks "how do we know the AI didn't make this up?" |
| [Data & source protection](docs/data-and-source-protection.md) | Before pointing it at anything sensitive |
| [Newsroom workflow](docs/newsroom-workflow.md) | You're fitting it into a desk with reporters, editors, and counsel |
| [Roadmap](docs/roadmap.md) | You want to know where this is going or how to adapt it to your beat |

## Provenance & license

Built by a team at Arizona State University — Evan (analysis engine), Steve (data
profiler & QA), Mitul (legal checker), Allie & Katie (case file), Shelby (footnoter).
The toolkit was developed and exercised on a complete federal-lobbying investigation
and a second run on Medicare hospital billing data; those materials live with the
original project, not in this repo. This edition is maintained for working newsrooms.
MIT license: use it, change it, ship it.
