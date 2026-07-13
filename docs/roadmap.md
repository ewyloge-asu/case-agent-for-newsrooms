# Roadmap

Where this is going, and how to bend it toward your beat today.

## Adapting it to your beat now

The honest current state: the analysis engine is mature for money-in-politics records,
and the *method* — scope, ingest, profile, find deviations, track, harden — is general.
The scoping step already synthesizes a starter plan for any beat, the profiler takes
any table, and the case file, legal checker, and footnoter are beat-agnostic. The
Medicare example in `examples/medicare-billing/` shows the full loop on a foreign beat.

What adapting to your beat looks like today: point the scoping step at your question,
let the data-finder locate your sources, profile with `robodoig`, and express your
beat's "what counts as unusual" as simple queries over the ingested records — the
lobbying engine's source is the worked example of that pattern.

## What's next (in order of intent)

1. **The engine/beat-pack split made explicit.** The lobbying-specific parts (entity
   keys, issue codes, anomaly rules, connectors) pulled into a swappable configuration,
   so a new beat is a config file plus connectors — not a code fork.
2. **More beat packs.** Procurement/contracts and healthcare billing are the natural
   next two; both have public bulk data and clear baselines.
3. **A richer editor dashboard.** Filtering, search, money timelines, coordination
   views — the current dashboard is deliberately minimal; the reporter-facing version
   is designed and not yet built.
4. **Cross-model verification.** Key analytical readings re-run against a second model
   and reconciled — aimed at interpretation errors, not arithmetic (the arithmetic is
   already deterministic).
5. **Onboarding for non-technical desks.** A guided setup that gets a reporter from
   zero to first result without touching a terminal.

## Contributing

The useful contributions, in order: run it on your beat and report what broke; share
the queries that expressed your beat's anomaly rules; harden a connector for a public
data source we don't cover. Issues and PRs at the repo. If you build a beat pack —
even a rough one — we want it.
