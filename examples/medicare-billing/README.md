# Case study: Medicare hospital billing

The same pipeline on a completely different beat — run to demonstrate that nothing in
the workflow is hardwired to lobbying. From a blank question to a ranked,
artifact-checked lead list in one session, with no lobbying-specific code involved.

## The question

*Which hospitals show billing patterns consistent with Medicare up-coding — billing
simple conditions at the highest severity tier?*

## What the pipeline did

1. **Scoped the beat** — the scoping step produced a healthcare investigation plan
   (entities, time frame, what counts as a finding) instead of falling back to its
   lobbying configuration.
2. **Found and kept the data** — the data-finder ranked CMS's public files first,
   queried a live state open-data portal, and surfaced the HHS Inspector General's
   up-coding report, which supplied the anomaly definition. Three live CMS data slices
   (simple pneumonia at its three severity tiers, 4,079 provider rows) and the OIG
   report were fetched and stored with checksums.
3. **Profiled, then measured against the baseline** — per-provider highest-severity
   billing shares versus the national median (74.4%); top outliers bill 90–92%,
   exactly the pattern the OIG flags for review.
4. **Flagged its own artifact** — the first pass showed a wall of hospitals at exactly
   100%. That turned out to be a small-cell suppression artifact in the CMS files;
   120 providers were excluded and the correction recorded.
5. **Filed it properly** — a case-file thread (status: chasing, next actions recorded:
   case-mix adjustment, multi-year trend, the sepsis DRG pair) and a generated
   dashboard.

## What's in this folder

| File / folder | What it is |
|---|---|
| `casefile/` | The brief, the beat plan, and thread T-0001 |
| `snapshots/` | The CMS slices + OIG report, checksummed |
| `found_sources.json` | The data-finder's output for the topic |
| `profile/` | The robodoig profile: stats, histograms, correlations |
| `leads_upcoding_signal.json` | 25 ranked leads, with method and caveats recorded |
| `review_dashboard.html` | The generated editor dashboard |

## The honest caveats (also recorded in the outputs)

These are **leads, not findings** — severity mix can reflect real patient acuity
(transfer centers, teaching hospitals). The recorded next steps are where a reporter
takes over. That handoff point — ranked, sourced, caveated leads — is the deliverable.
