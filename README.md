# Hi, I'm Gurnek 👋

**Program & Product leader in Toronto, now building AI products hands-on.**

15+ years turning vague, high-stakes mandates into things that ship. Now I'm building AI products of my own.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-gurnek--khaira-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/gurnek-khaira)
![Toronto](https://img.shields.io/badge/Based_in-Toronto,_ON-555?style=flat)
![PMP](https://img.shields.io/badge/PMP-certified-2E7D32?style=flat)
![PMI-ACP](https://img.shields.io/badge/PMI--ACP-certified-2E7D32?style=flat)

---

## 🔨 What I'm building

### [Redline](https://github.com/gurn3k/redline-review) · [Live demo ↗](https://redline-review-nine.vercel.app)

**Read it before you sign it.** Redline reviews a contract someone hands a small business owner *before* they sign. It gives a plain-English summary, severity-ranked risk flags, a drafted counter-offer for each flagged clause, and a Q&A box that answers only from the uploaded document.

The rule I built it around: **if Redline can't point to the exact sentence, it doesn't show the flag.** Every citation is machine-checked against the source text, and anything that can't be traced gets dropped before the user sees it.

- **Checks** personal guarantees, indemnification, auto-renewal, and unilateral termination in depth, plus generic detection for arbitration waivers and liability caps
- **Returns an explicit "Clear" result** that names what it checked, instead of an empty list
- **Built like a product, not a weekend hack:** a four-part market research pass, a PRD, 10 architecture decision records, 12 scoped tickets, and 48 automated tests
- **Stack:** Next.js · TypeScript · Supabase · OpenRouter · Vercel

### [AI PM Job Radar](https://github.com/gurn3k/ai-pm-job-radar) · [Live radar ↗](https://ai-pm-job-radar.vercel.app)

**Every PM, program and TPM opening at 36 AI companies, sorted in 15 seconds for 11 cents.** Job boards can't tell me what I actually need to know: is the product itself AI, does the role require hands-on ML, is it a program or product role, and can I do it from Toronto. The radar answers those for every open role.

The rule I built it around: **code computes facts, the model judges meaning.** The first version asked the model for location, and it labeled Vancouver roles as US-only. A location string is a fact, so it moved into code.

- **First full run:** 8,381 open roles scanned, 1,018 product and program roles labeled by [Jev](https://docs.typesafe.ai) in 15 seconds for $0.107, with 0 errors
- **Finding:** only 9 of 198 AI PM roles list hands-on ML experience as a must-have. Most AI product roles want judgment about AI, not a model-building background
- **Runs itself:** the live page refreshes every Monday with no manual steps, capped at $0.30 per run, and refuses to publish if more than 5% of labels fail or the role count halves
- **Measured against human judgment:** I hand-labeled 40 postings and scored the model against them. On the 18 labeled blind, it correctly sorted 15 into "AI role I'm targeting" or not. The eval also showed that "needs AI experience" covers two different requirements, an ML background and hands-on AI skills, so the radar now screens for each separately
- **Stack:** Python · Jev (TypeSafe) · Vercel · public Greenhouse, Ashby and Lever job boards

### 🚧 More on the way

Each product I build starts the same way: a real user, a specific pain, and one guarantee the product has to keep. Watch this space.

---

## 📈 How I got here

I've always learned by doing the next hard thing. I started by founding my own **implementation consultancy** and shipping 100+ SaaS, CRM, and eCommerce projects for small businesses. From there I led a CRM rollout at a **national telecom**. At a **multi-campus college**, I built a PMO from scratch across nine campuses and made the call on its overnight shift to digital when COVID hit. I brought generative AI into a **federal government department** under strict security rules. Today, at an **IT services firm**, I direct AI modernization programs for enterprise clients.

Each step went deeper into technology and closer to the product. Building my own AI products is the natural next one.

Full history on [LinkedIn](https://linkedin.com/in/gurnek-khaira).

---

## 🧰 Toolkit

**How I build:** I define the product (research, PRD, decision records, tickets, evaluation criteria) and direct AI coding agents in Claude Code to write the code.

**Products built on:** Next.js · TypeScript · Supabase · Vercel · OpenRouter · Python · Jev

**Certified in:** PMP · PMI-ACP · Professional Scrum Master I · Google Data Analytics · Google Business Intelligence

---

## 🤝 Let's connect

I'm open to **Senior Program Manager, Program Director, and Program/Product hybrid roles** at companies that put AI into their own products at real scale. Remote or hybrid in the GTA.

If you're building something like that, or want to talk about Redline or the Job Radar, [find me on LinkedIn](https://linkedin.com/in/gurnek-khaira).
