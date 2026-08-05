I'm Andrea, 16, from Italy. I build AI agents and automation tools, mostly for
problems I actually run into, and I handle web work for industrial clients
through my father's firm.

I don't hand-write the code. I work in Claude Code: I decide what gets built and
usually spot the behaviour that's off, it writes the implementation and finds the
bugs a few layers down. The calls are mine.

Most of what I've learned lately comes from one recurring problem: an LLM will
always hand you a confident answer, so the interesting engineering sits in
whatever is allowed to say no. Several of these repos are variations on that.

**[geopolitical-investment-agent](https://github.com/postagaspa-star/geopolitical-investment-agent)**
— multi-agent system that reads geopolitical events and runs a simulated
portfolio. A cheap model handles the high-volume news stages, Claude does
synthesis and the decision, and a layer of deterministic rules can veto an
outcome but never invent one. No performance claims here; it's an experiment in
decision architecture.

**[jarvis-2.0](https://github.com/postagaspa-star/jarvis-2.0)** — always-on agent
for Windows. Memory is Markdown on disk, and only the nightly consolidator is
allowed to mark a file as verified, so no agent grades its own homework.

**[stockmind](https://github.com/postagaspa-star/stockmind)** — began life as a
screener emitting BUY/HOLD verdicts. I rewrote it to explain companies instead,
and the backend now strips any verdict field the model tries to slip back in.

**[sol](https://github.com/postagaspa-star/sol)** — Android voice assistant built
for my father, who works on site with his hands full. Risk classification lives
in Kotlin, not in the prompt.

**[surplus](https://github.com/postagaspa-star/surplus)** — Android app for
tracking food and training through a calorie surplus. The one thing here that
gets used every day rather than built to learn from. It works offline and keeps
nothing off the phone; that repo is the landing page and the APK releases, not
the source.

**[pactum](https://github.com/postagaspa-star/pactum)** — parental control
inverted: the teenager writes their own rules, the parent verifies, and nothing
is ever blocked. I'm the teenager in it. Since the app can't stop anything, all
the value sits in whether its log can be trusted, so the strongest check lives
off the phone — the server watching for heartbeats that stop arriving.

**[task-sync](https://github.com/postagaspa-star/task-sync)** — an evening note
on Google Keep becomes tomorrow's tasks, spread across four services that all
have to end up agreeing with each other. Every write is flagged in SQLite before
it counts as done, so a job that dies at 2am resumes instead of duplicating.

Also worth a look: [devagent](https://github.com/postagaspa-star/devagent), a
coding agent whose server runs on Render while a local WebSocket bridge gives it
filesystem access, and
[stockAI-analyzer](https://github.com/postagaspa-star/stockAI-analyzer), the
first thing I built in this space, now archived.
