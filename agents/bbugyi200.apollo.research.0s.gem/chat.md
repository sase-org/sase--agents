# Chat History - ace-run (research.0s.gem)

- **TIMESTAMP:** 2026-10-10 14:32:02 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.0s.gem

## Prompt

%id(gem, clan=research.0s)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.0s.cdx`, `research.0s.cld`, `research.0s.grk`, `research.0s.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I am going to apply to one or two NYC DataBricks roles and I would like you to help me
design a CV specifically for this/these role(s).

- See the databricks_omnigent_job_fit.md file in the research sidecar repo for context.
- This CV should be modeled off of my existing CV in my bbugyi200/CV GitHub repo and
  should be committed to that repo.
- I left Google in May, but I haven't updated my LinkedIn or CV yet, so you should do
  that (or, in the case of LinkedIn, give me guidance on what needs to be done). During
  my 6 monthes unemployed I have been working on sase fulltime. I am currently working
  on releasing a blog post to http://sase.sh (it should be done within the next week or
  two) before I start my looking for a new role, but was so excited to hear about
  Omnigent that I figured I would try applying to DataBricks.
- I would also like to create a short pitch for each role that you think I should apply
  for (make sure I'm really qualified for each).

Can you do some research with the goal of helping me with all of this? 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Report: Databricks NYC Roles, CV Design, Tailored Pitches, and LinkedIn Strategy

**Researcher:** `gem` (5-researcher swarm)  
**Research Report File:** [`databricks_nyc_cv_design_pitches_and_linkedin__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202610/databricks_nyc_cv_design_pitches_and_linkedin__gem.md)  
**Registered Artifact:** `ref: file:explicit:f707be5b7a9764aefcffa094` (`research:202610/databricks_nyc_cv_design_pitches_and_linkedin__gem.md`)

---

## 1. Executive Summary & Recommended Roles

Databricks opened its New York City R&D Hub in January 2026 with a dedicated focus on agentic AI, LLMs, and core data infrastructure. Databricks' open-source meta-harness **Omnigent** solves the exact same problem as **SASE** ([sase.sh](https://sase.sh)): providing an abstraction and control layer over coding-agent CLIs, isolating work, governing human approval gates, and enabling deterministic evaluation.

Having spent the last six months (May–October 2026) architecting and maintaining SASE full-time, you are an immediate, high-signal match for two specific NYC roles:

### Primary Targets (Dual-Track Application)

1. **Staff Software Engineer, Agent Quality (NYC)**
   - **Job ID:** `8842963002` | **Base Salary:** $200,000 – $265,000
   - **Team & Focus:** Founding member of a new AI Research team building evaluation infrastructure and benchmark flywheels for Genie Agents and the agent platform.
   - **Why You Are Qualified:** 
     - SASE's `fakey` conformance harness simulates token limits, streaming interrupts, rate limits, and tool failures deterministically without model calls.
     - Your prior industry record at Edgestream (in-house test runner/framework improvements, `pylint` rollout across 1M+ LoC) and Bloomberg (Compliance SRE, Python cookiecutter, ChangeLog Driven Release methodology) directly proves test framework and reliability expertise.
     - SASE's 33+ Prometheus telemetry metrics demonstrate observability rigor.
   - **Preparation:** Build a small automated task-success evaluation script on SASE before interviewing.

2. **Senior Software Engineer – Backend (AI Platform) (NYC)**
   - **Job ID:** `8379331002` | **Base Salary:** $165,300 – $219,675
   - **Team & Focus:** Core backend team hiring across MLflow, Unity AI Gateway, Databricks Apps, Agent Framework, Agent Bricks, and Foundation Model APIs. **Commit history confirms that Omnigent maintainers sit inside this AI Platform org.**
   - **Why You Are Qualified:**
     - Safest level match (Senior SWE with ~7.4–8 years of experience).
     - SASE is a 1:1 conceptual analogue to Omnigent, unifying 7 agent CLIs behind a single provider interface with isolated git workspaces.
     - Production Python (3.12+), high-performance Rust core (`sase-core-rs`), and enterprise Java (Google Ad Manager).
     - Large-scale distributed systems experience at Google Ad Manager (billions of daily events, 99.99%+ SLA).
   - **Strategy:** Apply here and ask the recruiter for routing to the Omnigent, AI Gateway, or Agent Framework teams.

*(Note on Staff Backend SWE – Unity AI Gateway `8468436002`: Requires 8+ years and specifically asks for Scala or Go. Name this to the recruiter as a team interest under Role #2 rather than applying directly).*

---

## 2. CV Design & Committed Updates (`bbugyi200/CV`)

A dedicated Databricks CV variant is available and committed to the master branch of [bbugyi200/CV](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/external/gh/bbugyi200/CV):
- **Source:** [`BryanBugyi_Databricks_CV.tex`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/external/gh/bbugyi200/CV/BryanBugyi_Databricks_CV.tex)
- **PDF:** [`BryanBugyi_Databricks_CV.pdf`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/external/gh/bbugyi200/CV/BryanBugyi_Databricks_CV.pdf) (compiled with `pdflatex`, verified 2-page fit).

### Key Design & Content Highlights
- **Palette ("Databricks Flame & Slate"):** Uses Databricks signature flame red (`#FF3621`), deep spruce navy (`#1B3139`), slate metadata (`#5A6B73`), and IBM Plex Sans/Mono typography.
- **Header:** `Software Engineer — Agentic-AI Platforms, Evaluation & Systems` with links to email, phone, GitHub, LinkedIn, and `sase.sh`.
- **Experience Alignment:**
  - **SASE (sase.sh) (May 2026 – Present | Founder & Lead Software Engineer):** Framed as full-time lead engineering work across the 7-harness meta-platform, Rust domain core (`sase-core-rs`), AXE scheduler, `fakey` conformance harness, typed gates (plan/question/sudo), and Prometheus telemetry.
  - **Google (June 2022 – May 2026):** Accurately reflects your departure in May 2026; highlights large-scale distributed systems, Java backend services, billions of daily events, and 99.99%+ availability SLAs on Google Ad Manager.
  - **Bloomberg & Edgestream:** Emphasizes testing runners, `pylint` tooling, CI/CD automation, and SRE methodology.
- **Skills Categorized:** Highlighted `AI & Agentic Systems` (multi-agent orchestration, meta-harness design, agent evaluation, Claude Code, Codex, Antigravity) alongside Python 3.12+, Rust, Java, Linux internals, and distributed systems.

---

## 3. Short Role-Specific Pitches

### Pitch 1: Staff Software Engineer, Agent Quality (`8842963002`)
> "I have spent the last eight years building high-reliability testing frameworks, developer platforms, and distributed systems across Google, Bloomberg, and Edgestream. For the past six months, I have been working full-time on **SASE** (sase.sh), an open-source multi-agent developer platform that orchestrates seven coding-agent harnesses.
> 
> A central challenge in agent systems is test determinism and evaluation. In SASE, I engineered `fakey`—a deterministic conformance harness that simulates token limits, streaming interruptions, and tool failures without model calls—paired with Prometheus telemetry tracking 33+ agent lifecycle metrics. Combined with my prior experience integrating testing frameworks across million-line production codebases at Edgestream and Bloomberg, I understand how to turn agent behavior into reliable, reproducible evaluation data. I would love to bring this experience to Databricks' Agent Quality team to build the evaluation and flywheel infrastructure powering Genie Agents and the agent platform."

### Pitch 2: Senior Software Engineer – Backend, AI Platform (`8379331002`)
> "I am a backend and systems software engineer with eight years of experience building distributed systems and developer tools at Google Ad Manager (supporting billions of daily requests at 99.99%+ uptime) and Bloomberg SRE. For the past six months, I have worked full-time architecting and maintaining **SASE** (sase.sh), an open-source meta-harness platform that coordinates seven coding agents (Claude Code, Codex, Antigravity, OpenCode, and others) behind a unified Python/Rust backend with isolated git workspaces and typed approval gates.
> 
> SASE shares its foundational architectural DNA with Databricks’ **Omnigent** and Agent Framework. I have deep firsthand experience solving the hard problems of agent session orchestration, workspace isolation, and CLI adapter conformance. I am applying to Databricks’ AI Platform team in NYC with the goal of routing to Omnigent, Unity AI Gateway, or Agent Framework to build the next generation of scalable agent developer infrastructure."

### Pitch 3: Concise InMail / Referral Outreach (150 Words)
> "Hi [Name],
> 
> I saw that Databricks is expanding its Agentic AI and AI Platform engineering teams at the NYC R&D Hub.
> 
> Over the past six months, after four years engineering high-scale distributed backend services at Google Ad Manager, I’ve been working full-time building **SASE** (sase.sh)—an open-source meta-harness and developer platform that orchestrates seven coding-agent CLIs behind isolated workspaces, typed approval gates, and deterministic failure benchmarks.
> 
> Given the close architectural alignment between SASE and Databricks' **Omnigent** and Agent Framework, I am very interested in the **Staff SWE, Agent Quality** (`8842963002`) and **Sr. SWE, AI Platform Backend** (`8379331002`) roles in NYC.
> 
> Would you or a colleague have 10 minutes to connect or point me toward the hiring team?"

---

## 4. LinkedIn Profile Refresh & Launch Strategy

### Profile Updates
1. **Headline:**  
   `Software Engineer | Building SASE (sase.sh) — Open-Source Multi-Agent Developer Platform | Ex-Google, Bloomberg SRE`
2. **Add Position (SASE):**
   - **Title:** Founder & Lead Software Engineer
   - **Company:** SASE (Structured Agentic Software Engineering)
   - **Dates:** May 2026 – Present
   - **Location:** New York, NY
   - **Description:** Detail the meta-harness architecture, 7 coding-agent harnesses, Rust core (`sase-core-rs`), `fakey` deterministic evaluation bench, and Prometheus telemetry.
3. **Update Google Position:**
   - Set end date to **May 2026**.
   - Ensure bullets highlight distributed systems, high throughput, and Java backend scale on Google Ad Manager.
4. **Featured Section:**
   - Link 1: [sase.sh](https://sase.sh) (or the launch blog post once published).
   - Link 2: GitHub repository (`sase-org/sase`).
   - Link 3: Black PR #1132 string handling overhaul.

### LinkedIn Announcement Post (Timed with `sase.sh` Blog Launch)
When releasing your blog post to `sase.sh` over the next 1–2 weeks, publish this companion post:

> *Over the last six months, after four years at Google, I’ve been heads-down building something I believe developer platforms desperately need: a reliable, governable control plane for coding agents.*
> 
> *Today, I’m excited to share the launch post for **SASE (Structured Agentic Software Engineering)**: https://sase.sh*
> 
> *Most teams adopting coding agents run into the same hurdles: managing multiple agent CLIs, workspace contamination, runaway autonomous actions, and brittle evaluation loops.*
> 
> *SASE is an open-source meta-harness platform that:*
> *✔️ Unifies 7 agent harnesses (Claude Code, Codex, Antigravity, OpenCode, and more) behind a single provider abstraction*  
> *✔️ Isolates work in atomic, numbered git workspaces*  
> *✔️ Enforces human-in-the-loop typed approval gates (plan, questions, sudo) with persistent audit trails*  
> *✔️ Runs deterministic failure benchmarks with `fakey`, our zero-model-cost conformance harness*  
> *✔️ Combines a high-performance Rust core with a responsive Textual TUI and AXE scheduler*  
> 
> *Read the full architectural breakdown at https://sase.sh.*
> 
> *With SASE live, I’m actively looking forward to connecting with teams building the future of agentic developer platforms and evaluation infrastructure in NYC! #AI #AgenticAI #Python #Rust #OpenSource #DevTools*

---

## 5. Artifact & Turn Summary

- **Research Report Written to:**  
  `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202610/databricks_nyc_cv_design_pitches_and_linkedin__gem.md`
- **Durable SASE Artifact Registered:**  
  `sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202610/databricks_nyc_cv_design_pitches_and_linkedin__gem.md" -l "research:202610/databricks_nyc_cv_design_pitches_and_linkedin__gem.md"`  
  `id: explicit:f707be5b7a9764aefcffa094`
- **Finalizer Declaration:** Submitted and accepted for `commit` on repository `sdd:research`.
