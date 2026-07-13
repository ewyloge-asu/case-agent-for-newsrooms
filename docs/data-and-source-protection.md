# Data & source protection

Read this before pointing the toolkit at anything you wouldn't publish. It's short
because the honest answers are simple.

## What stays on your machines

Everything the *scripts* do is local. The records you ingest, the database they build,
the case file, the snapshots, the dashboards — all ordinary files on your computer or
your newsroom's storage. Nothing in this toolkit uploads your data anywhere, hosts
anything, or phones home. There is no server and no account.

## What leaves your machines

Two things, and you control both:

1. **Whatever your AI agent reads goes to its model provider.** This is a property of
   the agent (Claude Code, Cursor, Cowork), not of these skills — but it's the fact
   that matters. When the agent reads a query result, a case-file entry, or a document
   to reason about it, that content is sent to the provider's API. The design keeps
   this surface small (the agent reads small aggregates, not your bulk records), but
   small is not zero.
2. **Optional live lookups** hit public government APIs (FEC, Congress.gov, data
   portals) with your query terms. Skip the keys and the toolkit runs entirely from
   local data and bundled snapshots.

## The rules we'd set in your shoes

- **Public records: use freely.** Disclosures, filings, spending data — the material
  this toolkit is built for carries no source-protection risk.
- **Confidential source material: keep it away from cloud agents.** Don't point an
  agent at leaked documents, whistleblower communications, or anything whose existence
  is itself sensitive — unless your organization has an enterprise AI agreement
  (zero-retention, no-training) that your leadership and counsel have actually read,
  or you're running a local model. The deterministic scripts work fine on sensitive
  data *without* the agent; it's the agent layer that transmits.
- **Check your provider terms once, in writing.** Consumer AI terms and enterprise
  terms differ on retention and training. Whoever owns AI policy in your newsroom
  should make this call once, not each reporter per story.
- **Named people in working notes.** Case files accumulate names and allegations long
  before anything is verified. Treat the case-file directory with the same access
  discipline as your reporting notes — it's a plain folder; put it where your notes
  live, not in a public repo.

## Retention & the paper trail

The flip side of provenance: this toolkit deliberately keeps receipts — snapshots with
checksums, append-only journals, session traces. That's an asset at publication time
and a liability if you treat working files carelessly. Decide where case files live and
who can read them the same way you would for any investigation folder.
