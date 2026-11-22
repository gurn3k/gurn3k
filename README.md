# Hi, I'm Gurnek 👋

**Program & Product Leader in Toronto, building AI products hands-on.**

15+ years running programs where being wrong is expensive. The rule I work by: decide what the outcome has to guarantee before deciding how to build it. The stack, the sequencing, and what gets automated all follow from that.

[![Website](https://img.shields.io/badge/Website-gurn3k.com-0E3B33?style=flat)](https://www.gurn3k.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-gurnek--khaira-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/gurnek-khaira)
![Toronto](https://img.shields.io/badge/Based_in-Toronto,_ON-555?style=flat)
![PMP](https://img.shields.io/badge/PMP-certified-2E7D32?style=flat)
![PMI-ACP](https://img.shields.io/badge/PMI--ACP-certified-2E7D32?style=flat)

---

## 🧭 Start here

Two minutes, three links:

- **Shipping LLM features people can trust.** [Redline](https://github.com/gurn3k/redline-review) drops any flag it can't tie to an exact sentence in the document. Its [eval](https://github.com/gurn3k/redline-review/blob/main/eval/REPORT.md) scores recall, precision and groundedness against planted answers and states its limits, and a [live adversarial test](https://github.com/gurn3k/redline-review/blob/main/docs/FINDINGS.md) included a prompt-injection attempt that didn't change the flags.
- **Measuring a model before trusting it.** For [AI PM Job Radar](https://github.com/gurn3k/ai-pm-job-radar) I [hand-labelled 40 postings](https://github.com/gurn3k/ai-pm-job-radar/blob/main/eval/RESULTS.md) and scored the model against them. Code computes facts, the model judges meaning, and answers it isn't sure of go to a review pile.
- **Program management on real engineering data.** [Whose Move Is It](https://github.com/gurn3k/whose-move-is-it) shows where 2,893 Kubernetes pull requests wait, by team and stage, and is [cross-checked](https://github.com/gurn3k/whose-move-is-it/blob/main/docs/research/devstats-cross-check.md) against Kubernetes' own DevStats.

---

## 🔨 What I'm building

### <img src="assets/icons/redline.svg" width="22" height="22" align="absmiddle" alt=""> [Redline](https://github.com/gurn3k/redline-review) · [Live demo ↗](https://redline-review-nine.vercel.app) · [Sample analysis ↗](https://redline-review-nine.vercel.app/sample)

**Read it before you sign it.** Redline reviews a contract someone hands a small business owner *before* they sign. It gives a plain-English summary, severity-ranked risk flags, a drafted counter-offer for each flagged clause, and a Q&A box that answers only from the uploaded document.

The rule I built it around: **if Redline can't point to the exact sentence, it doesn't show the flag.** Every citation is machine-checked against the source text, and anything that can't be traced gets dropped before the user sees it.

- **Checks** personal guarantees, indemnification, auto-renewal, and unilateral termination in depth, plus generic detection for arbitration waivers and liability caps
- **Returns an explicit "Clear" result** that names what it checked, instead of an empty list
- **See it without signing up:** a public sample shows a real, unedited review of a refrigeration service contract, with every flag tied to its highlighted sentence
- **Built like a product, not a weekend hack:** a four-part market research pass, a PRD, 12 architecture decision records, 13 scoped tickets, and 97 automated tests
- **Redesigned for the people who visit:** every page was reworked after a before-and-after review of three visual directions, and readers can sign in with Google or LinkedIn
- **Measured against planted answers:** I ran the real pipeline over a 9-document set with 30 in-scope planted clauses. It found 18 of 30 (60%), 18 of 19 flags shown matched a planted clause, every flag shown quoted its document word for word, and all 3 clean documents came back Clear. A model wrote the set, so I treat these as an upper bound and not a promise to users
- **Used the eval to fix the weakest category:** late fees and fee escalators were found 1 of 9 times. After widening one paragraph of the prompt, two further runs found 8 of 9 and 7 of 9, and overall recall rose from 18 to 25 and 24 of 30
- **Stack:** Next.js · TypeScript · Supabase · OpenRouter · Vercel

### <img src="assets/icons/job-radar.svg" width="22" height="22" align="absmiddle" alt=""> [AI PM Job Radar](https://github.com/gurn3k/ai-pm-job-radar) · [Live radar ↗](https://ai-pm-job-radar.vercel.app)

**Every PM, program and TPM opening at 36 AI companies, sorted in 15 seconds for 11 cents.** Job boards can't tell me what I actually need to know: is the product itself AI, does the role require hands-on ML, is it a program or product role, and can I do it from Toronto. The radar answers those for every open role.

The rule I built it around: **code computes facts, the model judges meaning.** The first version asked the model for location, and it labeled Vancouver roles as US-only. A location string is a fact, so it moved into code.

- **First full run:** 8,381 open roles scanned, 1,018 product and program roles labeled by [Jev](https://docs.typesafe.ai) in 15 seconds for $0.107, with 0 errors
- **Finding from the first run:** only 9 of 198 AI PM roles list hands-on ML experience as a must-have. Most AI product roles want judgment about AI, not a model-building background
- **Runs itself:** the live page refreshes every week with no manual steps, capped at $0.30 per run, and refuses to publish if more than 5% of labels fail or the role count halves. A same-day backup run covers a missed refresh, and a freshness check flags the page if its data is more than 8 days old
- **Measured against human judgment:** I hand-labeled 40 postings and scored the model against them. On the 18 labeled blind, it correctly sorted 15 into "AI role I'm targeting" or not, and answers it isn't confident in go to a review pile instead of being guessed. The eval also showed that "needs AI experience" covers two different requirements, an ML background and hands-on AI skills, so the radar now screens for each separately
- **Stack:** Python · Jev (TypeSafe) · Vercel · public Greenhouse, Ashby and Lever job boards

### <img src="assets/icons/whose-move.svg" width="22" height="22" align="absmiddle" alt=""> [Whose Move Is It](https://github.com/gurn3k/whose-move-is-it) · [Live report ↗](https://whosemoveisit.gurn3k.com)

**Where Kubernetes pull requests wait.** Kubernetes already publishes velocity charts. This answers the narrower question a program lead actually asks: right now, which team-and-stage queue holds the most waiting work, and is each open PR waiting on a reviewer, an approver, or its own author?

The rule I built it around: **every number opens the pull requests behind it.** The report has over 200 clickable numbers, and the unit of analysis is always a team and a stage, never a person.

- **Snapshot of 2026-11-21:** 1,526 merged and 1,367 open PRs. The median PR waits 2.9 days for review, then merges in 1.7 hours once approved. The bottleneck is review, not the merge queue
- **Finding:** 295 open PRs (22% of the backlog) have never had a human response, at a median wait of 37 days. 641 open PRs (47%) wait on a reviewer or approver, against 383 waiting on their author
- **Cross-checked against Kubernetes' own DevStats, twice:** the pattern is the same both times. The medians now differ more than on the first run, and the write-up says what is and isn't known about why
- **An AI brief that can't make things up:** a small model writes the risks summary, and code rejects any bullet that cites a PR not in its input or a number not in the computed data. If no bullet passes, the report ships without a brief. Each call is capped at US$0.05
- **Built from a spec, with 73 tests:** a PRD, 10 decision records, 8 tickets, and automated tests covering the metrics, the brief's fact checks, the GitHub fetcher (run against a recorded API response), and the public page itself, including a check that every count opens exactly that many pull requests
- **Stack:** Node.js · GitHub API · OpenRouter · Vercel

### <img src="assets/icons/cap-drafter.svg" width="22" height="22" align="absmiddle" alt=""> [Cap Drafter](https://github.com/gurn3k/auction-draft-tool-kit) · [Live app ↗](https://fan-basketball-drafter.vercel.app) · [88-second demo ↗](https://www.gurn3k.com/work/cap-drafter)

**Live auction prices for fantasy basketball salary cap drafts.** Basketball is a passion of mine, and this is the tool I wanted for my own drafts. Yahoo's draft room shows a fixed price for each player. That price ignores your league's budget and everything that has already sold. Cap Drafter prices every player for your league and re-prices the board after every sale, under a 30-second bid clock.

The rule I built it around: **every price has to add up to exactly the money left in the room.** With Yahoo defaults, 156 players are priced at exactly $2,400. After each sale, the live prices share out exactly what's left. Tests check both.

- **Bid to, not just value:** the live price, tilted up to ±20% toward the categories my roster is losing, and capped at what I can actually bid
- **Dropped my own data source before launch:** Basketball-Reference's terms rule out tools built on scraped data. I compared five alternatives, moved to a licensed API, and checked that all 582 players' stats matched exactly
- **Parked a finished feature rather than shipping one that couldn't work:** Yahoo sign-in and live draft sync were built, then Yahoo started requiring approval for its Fantasy API. I've applied, and sync waits on a branch until approval comes through. A read-only Chrome side panel is next, one that never reads Yahoo's pages. I've emailed Yahoo about its use, and it waits on the same approval
- **Used in a live draft run**, with 12 decision records and 90 automated tests
- **Reviewed before it went further:** a review pass found 18 problems, such as prices that stopped adding up in some leagues. All 18 are fixed with tests, and [the findings](https://github.com/gurn3k/auction-draft-tool-kit/blob/main/docs/FINDINGS.md) list what's still open
- **Stack:** vanilla JavaScript · balldontlie API · Vercel. No framework, no build step

### <img src="assets/icons/judging-the-judge.svg" width="22" height="22" align="absmiddle" alt=""> [Judging the Judge](https://github.com/gurn3k/llm-output-quality-scoring-guide) · [Findings report ↗](https://www.gurn3k.com/judging-the-judge/)

**Can you trust an AI model to grade other AI output?** Teams shipping AI features increasingly let one model judge another's replies, and most never check that judge against a person. I measured one on 216 customer support replies with planted failures, against an answer key and my own blind labels.

The rule I built it around: **every figure in the report comes from the run files.** The page won't build if a number is typed by hand, and a test checks each one against the data.

- **Clear criteria held up:** Claude Sonnet 5.5 caught 189 of 196 planted failures and agreed with the answer key on 95% of verdicts (kappa 0.86)
- **Vague criteria hid their damage:** the catch rate stayed at 193 of 196 while agreement fell to 65%, because the judge also failed 297 verdicts that should have passed. Catch rate alone would have called the vague criteria better, and a stronger judge didn't fix it: Opus 5.5 reached kappa 0.48 against Sonnet's 0.46
- **Trust takes more labels than you'd think:** 40 labels couldn't settle a single criterion. It took 160 to settle three of the four
- **The priciest model isn't automatically the right judge:** Opus 5.5 agreed slightly more, at 2.3 times Sonnet's cost. Haiku 5.5 was by far the cheapest but obeyed an instruction hidden in a reply
- **Built to scale from the first version:** 85% of input tokens came from the prompt cache, 1 of 1,760 calls needed a retry, and spending caps and resume were there from the start. The report also says what would give way first
- **Checked against my own labels:** 30 replies labelled blind agreed with the answer key on 116 of 120 labels. $6.26 spent judging, and 129 automated tests
- **Stack:** vanilla JavaScript · Node.js · Anthropic API. No dependencies

### <img src="assets/icons/understudy.svg" width="22" height="22" align="absmiddle" alt=""> [Understudy](https://github.com/gurn3k/understudy) · [Findings report ↗](https://understudy.gurn3k.com)

**Can an AI pass invoices straight to payment, and how would a company prove it first?** Companies keep asking where AI should take over work people do today, and the evidence is usually a demo. On a real company's 2018 purchasing records, I tested three approaches, two of them AI, on held-out invoices: the simple rule and the rulebook on 54,874, and Claude checking each invoice on a 10,000-invoice follow-up. I checked every call against what really happened.

The rule I built it around: **an AI is trusted only when its worst likely case clears the bar.** Of the invoices it pays without a check, at least 99 in 100 must turn out fine, with enough of them to rule out luck. Every rule was written down before the run it governs, and the 11 changes made after a result was known are listed on the page.

- **Result: not proven.** Claude writing a rulebook that ordinary code runs paid 48.7% of invoices on its own, and 99.07% of those were fine. Its worst likely case was 98.95%, or 98.82% allowing for invoices on the same order, so it did not prove the bar. A simple rule paid nothing
- **Claude checking each invoice:** in a follow-up on 10,000 new invoices, set up in writing before it ran, it paid 577 (5.8%) and 6 of those needed a correction, so it could not show 99%. The rulebook costs $0.40 once. Checking each invoice costs $2.60 per 1,000, every time
- **Earning trust one kind of invoice at a time:** a week-by-week replay switched the AI on for a kind of invoice only once its real outcomes proved the bar. It switched a kind off again when results slipped. It paid 844 lines, 15 of which needed a correction, all in one kind. Outcomes arrive weeks late, so trust comes slowly
- **The agreement trap:** in a simulation where reviewers copy the AI 9 times in 10, switching it on by agreement let through about ten times as many lines that needed a correction. The agreement measured the reviewers, not the AI
- **A model pilot, in two documents:** a request for proposals to send to suppliers, and the internal business case with a calculator for the reader's own inputs. The return verdict stays out of the request
- **Built to be checked:** 30 decision records and 137 unit tests. A second program, written separately, recounted the 1.6 million-event log. A pre-registered check on a later month (September 2018) ran once. Another check confirms that every fixed sentence appears word for word on the page
- **Stack:** Python (standard library) · vanilla JavaScript · Claude · Vercel. No dependencies

### 🚧 More on the way

Each product I build starts the same way: a real user, a specific pain, and one guarantee the product has to keep. Watch this space.

---

## 📈 How I got here

I've always learned by doing the next hard thing. I started by founding my own **implementation consultancy** and shipping 100+ SaaS, CRM, and eCommerce projects for small businesses. From there I led a CRM rollout at a **national telecom**. At a **multi-campus college**, I built a PMO from scratch across nine campuses and made the call on its shift to digital in under two weeks when COVID hit. I brought generative AI into a **federal government department** under strict security rules. Today, at an **IT services firm**, I direct AI modernization programs for enterprise clients.

Each step went deeper into technology and closer to the product. Building my own AI products is the natural next one.

Full history on [LinkedIn](https://linkedin.com/in/gurnek-khaira).

---

## 🧰 Toolkit

**How I build:** every product starts with research, a PRD, decision records, tickets and evaluation criteria, and ships with real numbers from real runs.

**How I measure:** gold sets with planted answers, precision, recall and groundedness scores, hand-labelled samples, and a model judge checked against my own labels. Results are reported as they came out.

**Products built on:** Next.js · TypeScript · Supabase · Vercel · OpenRouter · Python · Jev · Node.js · GitHub API · vanilla JavaScript · balldontlie API · Anthropic API

**Certified in:** PMP · PMI-ACP · Professional Scrum Master I · Google Data Analytics · Google Business Intelligence

---

## 🤝 Let's connect

I'm open to **Program, Technical Program or Product Management roles** in organizations building AI at scale. Remote or hybrid in the GTA.

If you're building something like that, or want to talk about Redline or the Job Radar, see [gurn3k.com](https://www.gurn3k.com) or [find me on LinkedIn](https://linkedin.com/in/gurnek-khaira).
