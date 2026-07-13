# Fitting it into a newsroom

Case Agent has three surfaces, and they map onto a desk the way you'd hope.

## Who touches what

**The reporter drives, in chat.** The agent conversation is where the investigation
happens: scoping the question, running the analysis, chasing leads, deciding what's
worth another session. The reporter's judgment is a designed-in control point — the
scoping step interviews them, and the pipeline pauses for a human call wherever the
data suggests changing course.

**The editor reads the dashboard.** One command generates a single HTML page from the
case file: every lead and its status, the verified findings, the legal flags — each
claim linked to its source record. No login, no software; it opens in a browser and
prints. This is the story-meeting artifact.

**Counsel gets the legal memos.** The legal checker produces written element-by-element
memos (statute text quoted, facts tested against each element, verdict capped at
"possible / unclear"). They're built to be forwarded to a lawyer as-is — a starting
memo, not a conclusion.

**The fact-checker gets the footnoted draft.** The footnoter returns the reporter's own
draft with each claim footnoted to its source as Word tracked changes, plus margin
comments wherever support is missing or a quote may be out of context. Checking becomes
reviewing footnotes instead of re-reporting the story.

## Across days and weeks

The case file is the desk's shared memory. It's a plain folder — brief, one file per
lead with a status (open / chasing / confirmed / cold), an entity registry, a session
journal. Concretely:

- A new session starts with *"read the case file and pick up where we left off"* — no
  re-briefing the agent, no re-explaining the story to a tool.
- A second reporter joining mid-investigation reads `brief.md` and the thread files and
  is oriented in ten minutes — same as a good story memo.
- Dead ends stay dead. A closed lead records why it was closed and what evidence
  closed it, so nobody burns a week re-chasing it in month three.

## A realistic first project

Don't start with your most sensitive investigation. Pick something with public bulk
records and a real question — permit data, spending disclosures, inspection reports.
The rhythm that works:

1. One sitting: scope it with the agent, ingest the records, profile them, look at the
   first ranked leads. (This is an afternoon, not a sprint.)
2. Reporter picks the two or three leads worth shoe leather; the rest get statuses.
3. Editor sees the dashboard at the story meeting; decides what graduates to a story.
4. Drafting stays human. The footnoter runs on the draft before it goes to the desk.

## What this doesn't replace

Sourcing, interviews, FOIA strategy, news judgment, and the writing. The toolkit
compresses the records work that surrounds those things — the part that used to decide
whether a data-heavy story was affordable at all.
