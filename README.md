I'm Andrea, 16, from Italy. I build AI agents and automation tools, mostly for
problems my family and I actually run into, and I handle [web work for industrial
clients](https://stgm.eu/sitiweb.html) through my father's firm.

I don't hand-write the code. I work in Claude Code, often starting from a prompt
I've drafted in a separate Claude chat: I decide what gets built and in what
order, and I test it on the real phone, which is where I find most of the
behaviour that's off. Claude writes the implementation, chooses most
of the architecture and finds the bugs a few layers down, and it introduces some
too, which is why the testing stays with me. The product calls are mine and so is
the last word on design, although the options I pick from usually come from Claude.

Most of what I've learned lately comes from one recurring problem. An LLM will
always hand you a confident answer, so the interesting engineering sits in
whatever is allowed to say no. That isn't my instinct, since I usually want the
model to do more, so it's a lesson I keep relearning, and several of these repos
are variations on it.

**[wisper](https://github.com/postagaspa-star/wisper)** lets an industrial
technician file the daily work report by talking, without touching the phone:
gloves on, both hands busy, and anything that needs a screen has already lost. Two
days, for NGN Hacks 2026. It is also the cleanest example of the rule above: the
summary Wisper reads back at the end is assembled from the stored fields and
never written by the model, because a technician who isn't looking at the screen
hears "forty kilometres" and believes it. Then my father, the technician it was
for, tried it and told me to drop the voice and let him do it by hand, so the
version now on a branch is a rewrite without it: a phone app for the site, a
desktop program for invoicing at the office, and the same Google Sheet underneath.

<img src="https://raw.githubusercontent.com/postagaspa-star/wisper/main/docs/immagini/5-scheda.png" width="200"> <img src="https://raw.githubusercontent.com/postagaspa-star/wisper/main/docs/immagini/4-domanda.png" width="200"> <img src="https://raw.githubusercontent.com/postagaspa-star/wisper/main/docs/immagini/3-ascolta.png" width="200">

*One spoken sentence becomes the report; a dash is a field it doesn't have yet and asks for, one at a time; the microphone is there because a colour has to be learned and a microphone does not.*

**[Arena](https://github.com/postagaspa-star/arena)** reads every project
submitted to a Devpost hackathon, opens the code they linked, and scores all of
them against that hackathon's own criteria, mine included, with the names
stripped so it can't tell which one is mine. It keeps the model outside the loop:
it looks at one page of each kind and writes the CSS selectors, then a
deterministic engine applies them to 900 pages. Three inferences instead of
2,500. Each score carries the spread between independent passes, so a project is
`412 ± 18` and anything overlapping that band is a tie rather than a rank.

<img src="https://raw.githubusercontent.com/postagaspa-star/postagaspa-star/main/immagini/arena.png" width="700">

*How much it failed to measure sits at the same size as how much it did. Each criterion is a strip: every other project is a grey tick on the same track, the median is a hairline, and the dot is you. Shown here on the example data the repo ships with, which deliberately doesn't place you first.*

**[geopolitical-investment-agent](https://github.com/postagaspa-star/geopolitical-investment-agent)**
is a multi-agent system that reads geopolitical events and runs a simulated
portfolio. A cheap model handles the high-volume news stages, Claude does
synthesis and the decision, and a layer of deterministic rules can veto an
outcome but never invent one. There are no performance figures in it; the point
was the decision architecture.

**[jarvis-2.0](https://github.com/postagaspa-star/jarvis-2.0)**, an always-on
agent for Windows. Memory is Markdown on disk, and only the nightly consolidator
can mark a file as verified, so nothing gets to certify its own output.

**[stockmind](https://github.com/postagaspa-star/stockmind)** began life as a
screener emitting BUY/HOLD verdicts. I rewrote it to explain companies instead,
and the backend now strips any verdict field the model tries to slip back in.

**[sol](https://github.com/postagaspa-star/sol)** is a mail assistant for my
father, whose working day disappears into his inbox. It sorts every message,
drafts the replies in the background and keeps track of what is still waiting
for an answer, running on our home NAS with open-weight models only. The models
have no tools, so a hostile email can at worst produce a bad draft, and nothing
is sent until he clicks on the exact version he read. It started as a hands-free
voice assistant, until it became clear that the problem was the inbox rather
than his hands.

**[surplus](https://github.com/postagaspa-star/surplus)**, an Android app for
tracking food and training through a calorie surplus. It's the one thing here
that gets used every day rather than built to learn from. It works offline and
keeps nothing off the phone, and the advice on what to eat next comes from fixed
rules rather than a model, so it can always say why.

**[normaai](https://github.com/postagaspa-star/normaai)** is a retrieval
assistant over an Italian municipality's building and planning rules. In this
domain a confident wrong answer doesn't stay in a chat window, it ends up in a
building application, so confidence is computed from how much of the answer is
actually covered by citations rather than stated by the model.

**[pactum](https://github.com/postagaspa-star/pactum)** inverts parental control:
the teenager writes their own rules and the parent verifies. I'm the teenager in
it. It started from never blocking anything, and only two exceptions have been
let in since, both named in the log: a study session I switch on myself, and
household chores my parents can set, which lock the phone and the computer until
each one has a photo of the finished job. Everywhere else the app can't stop anything, so the value sits in
whether its log can be trusted, and the strongest check lives off the phone, on
a server watching for heartbeats that stop arriving.

**[task-sync](https://github.com/postagaspa-star/task-sync)** turns an evening
note on Google Keep into tomorrow's tasks, spread across four services that all
have to end up agreeing with each other. Every write is flagged in SQLite before
it counts as done, so a job that dies at 2am resumes instead of duplicating.

Also worth a look: [devagent](https://github.com/postagaspa-star/devagent), a
coding agent whose server runs on Render while a local WebSocket bridge gives it
filesystem access, and
[stockAI-analyzer](https://github.com/postagaspa-star/stockAI-analyzer), the
first thing I built in this space, since replaced by stockmind.
