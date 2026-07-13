# Case study: federal lobbying money

A complete investigation run with these tools on federal lobbying records
(Senate/House LDA filings, LD-203 contributions, congressional press releases,
2022–2026 Q1; headline numbers from 2025). Included here exactly as the tools produced
it — findings, case file, legal memos, and the editor dashboard — as a worked example
of what the pipeline delivers.

## What it found

- **Money finds the gatekeepers** *(verified)* — 2025 contributions reported by
  registered lobbyists concentrate on the members who control whether legislation
  moves. Top recipient: Rep. Brett Guthrie (Chair, House Energy & Commerce), $694,295
  from 177 distinct lobbying registrants; lobbyist money runs 13–18% of the
  money-committee chairs' total campaign receipts. Pattern claimed; causation not.
- **A foreign-influence disclosure gap** *(verified)* — Tencent's lobbying jumped
  $800K → $4.04M while it fought a Pentagon designation, and the former White House
  official lobbying for it appears nowhere in the foreign-agents registry. Lawful; the
  finding is the lighter of two disclosure regimes permitting exactly this.
- **No one validates the filings** *(flagged for counsel)* — a Delaware filer reported
  $80M of "lobbying income" with no lobbying behind it, the largest "client" in the
  2025 data.
- **A closed lead, kept on purpose** — 36,643 matched Senate↔House filings, zero
  meaningful gaps; recorded with its evidence so it isn't re-chased.

## What's in this folder

| File / folder | What it is |
|---|---|
| `findings_report.md` | The full findings, every claim source-stamped |
| `casefile/` | The real case file: threads with statuses, entities, journal |
| `legal_checks/` | The two element-by-element legal memos, as produced |
| `review_dashboard.html` | The editor dashboard generated from the case file |
| `traces/` | Every skill invocation that produced the work, with verbatim outputs |
| `footnoter_demo/` | The findings draft footnoted to the pipeline's own outputs |

## Reproduce it

The records themselves are the corpus distributed for Northwestern's GAIN challenge
(not redistributable here); with a copy at `GAIN_DATA_DIR`, the whole thing re-runs
offline — commands are at the top of `findings_report.md` and in each trace entry.
Without the corpus, the demo slice bundled with `lobbying-influence-mapper` reproduces
the method (including the $80M outlier) in miniature.

## Two methods lessons this example carries

1. **Amendment-aware de-duplication.** Naively summing filings triple-counted a $80M
   outlier as $180M and manufactured 19 phantom cross-chamber gaps. Keeping only the
   latest filing per quarter fixed both — and is now built into the engine.
2. **The resolver decides the story.** Until honoree names resolved properly, the #1
   recipient in the data was invisible in the results. Entity resolution isn't
   plumbing; it's the finding's foundation.
