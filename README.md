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

Also worth a look: [devagent](https://github.com/postagaspa-star/devagent), a
coding agent whose server runs on Render while a local WebSocket bridge gives it
filesystem access, and
[stockAI-analyzer](https://github.com/postagaspa-star/stockAI-analyzer), the
first thing I built in this space, now archived.
