# Getting started

Fifteen minutes to a first result. You need **Python 3.9+** and either an AI coding
agent (Claude Code, Cursor, or Cowork) or just a terminal.

## 1 · Install the skills

Clone or download this repo, then copy the skill folders into your agent's skills
directory:

```bash
# Claude Code (all projects)
cp -r skills/* ~/.claude/skills/

# Claude Code (one project only)
cp -r skills/* your-project/.claude/skills/

# Cursor
cp -r skills/* ~/.cursor/skills/
```

Using an agent without Agent Skills support, or none of the above? The universal
fallback is one instruction: *"Read skills/investigative-method/SKILL.md and follow
it."* The SKILL.md files are the manual; any code-executing agent can work from them.

## 2 · Prove it runs (bundled demo data, no setup)

Every skill ships a small demo dataset. Ask your agent:

> Use the lobbying-influence-mapper skill on its demo data: ingest, resolve entities,
> and show me the top recipients of lobbyist contributions.

Or from a plain terminal:

```bash
cd skills/lobbying-influence-mapper
export GAIN_DATA_DIR=$PWD/demo_data GAIN_WORKDIR=/tmp/casework
python3 scripts/ingest.py --years 2025 --datasets senate contributions press
python3 scripts/resolve_entities.py
python3 scripts/xref.py gatekeeper --filer lobbyist --year 2025 --top 10
```

You should see a ranked leaderboard in a few seconds. Every row carries a provenance
ID; feed any of them to `scripts/review.py "<id>"` to see the raw filing behind it.

## 3 · Start a real investigation on YOUR beat

This is the intended entry point — not the lobbying data. Ask your agent:

> Use the investigative-method skill. I want to investigate [your question] using
> [where your records live].

The agent will interview you — the question, the entities, the time frame, what counts
as a finding — and set up a case file. From there:

- **Tabular records** (CSV, Excel, database exports): the agent profiles them with
  `robodoig` before anyone trusts a number.
- **Need data you don't have?** `investigative-method`'s data-finder suggests public
  datasets and official APIs for your topic, and snapshots whatever you pull in.
- **Every session after the first**, ask the agent to *"read the case file and pick up
  where we left off."* That's the point of the case file.

## 4 · Optional extras

- **API keys** (all free): FEC and Congress.gov keys unlock live refreshes of campaign
  finance and legislation data. `python3 setup_keys.py` walks you through it. Nothing
  requires a key — bundled snapshots cover the shipped examples offline.
- **Extra Python packages**: only two skills need any. `robodoig` wants
  `pandas numpy matplotlib openpyxl`; the footnoter wants `python-docx lxml` (plus
  `pdfplumber` for PDF sources). Each says so clearly if missing. Everything else is
  standard library.
- **Data conventions** (where the tools look for records and write outputs):
  [data-setup.md](../data-setup.md).

## Troubleshooting

- *"The agent doesn't trigger the skill"* — name it explicitly ("use the
  investigative-method skill") or use the universal fallback instruction above.
- *"Where did my results go?"* — generated artifacts live under `GAIN_WORKDIR`
  (defaults to `build/` in the working directory); the case file lives wherever you
  told the scoping step to put it.
- *"Something crashed on my weird CSV"* — that's a bug we want.
  [Open an issue](https://github.com/ewyloge-asu/case-agent-for-newsrooms/issues) with
  the error text; don't attach sensitive data.
