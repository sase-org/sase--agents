# Chat History - ace-run

- **TIMESTAMP:** 2026-07-17 10:01:31 EDT
- **MODEL:** claude/opus
- **AGENT:** research.g.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260717_094120.md`

## Prompt

%name:research.@.cld %m:@research_b %g:research %family(research.@.final, role=researcher) #gh:gh_sase-org__sase Can you do some research on best-practices for top-level README.md files in GitHub projects with the goal of helping me improve this project's README.md file? End your analysis with a list of recommended changes I should make to this project's README.md file. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by reading the current README.md to understand what we're working with, then research best practices.

The README is already in decent shape. Let me open the research sidecar repo properly and kick off web research in parallel.

Path confirmed. Now let me check existing report conventions and start the research fan-out.

Research repo conventions are clear. Now I'll fan out four parallel research agents covering different angles.

I'll load the web tools first, then start researching.

I'll research the primary sources in parallel batches. Starting with GitHub's official docs and the standard-readme spec.

I'll start by loading the web tool schemas, then work through each research area systematically.

I'll start with the core Prana et al. paper, which is the anchor citation.

I'll start by opening each peer repo as an external repo, then analyze their READMEs.

The standard-readme fetch was a summary — per my repo-access rules I should read that repo's files from a local checkout rather than over the web. Let me open it properly while fetching the non-repo sources.

Found the anchor paper. Let me pull the actual numbers from primary sources.

I'll start by exploring the repository structure and reading the key files.

Four research agents are running in parallel: canonical guidance (GitHub docs, standard-readme, Diátaxis), empirical/academic literature, a structural teardown of peer project READMEs, and a factual audit of sase's current README and docs. While they work, let me gather a bit of ground truth myself on the demo assets, since GIF weight is a common README problem.

README read. Now let me gather the supporting docs, demos, and metadata in parallel.

Both checkouts are open. Now reading the actual spec files locally.

The Springer version is paywalled. Let me find the open-access preprint and dig into the other threads in parallel.

Now the GitHub community standards docs, opensource.guide, and Diátaxis.

Two concrete findings already while the agents work: the README's four hero media files total roughly **7.1 MB** (`sase_overview.png` 1.4M + the three GIFs at 3.8M/774k/1.1M), and the GIFs are 1920×1080 rendered down to an 830px display width — about 2.3× oversized for how they're shown. Smaller `.mp4` counterparts of every GIF already exist in `demos/out/`.

Let me wait for the four research agents to report back.

README is 109 lines / 552 words — lean, which is generally a virtue. Waiting on the research agents now.

Now let me pull the authoritative open-access sources in parallel.

Exactly **7.03 MB** of media loads on every README view, with the multi-model fan-out GIF alone at 3.84 MB. That's a solid, verified finding to build on. Now I'll wait for the four agents to report.

All four opened. Let me open the remaining three.

Confirmed: no `SECURITY.md`, no `CODE_OF_CONDUCT.md`, and `.github/` has only `workflows` (no issue or PR templates). `CONTRIBUTING.md` exists but the README never links to it — it routes to `sase.sh/development/` instead. Now I'll wait for the research agents.

Two more gaps worth noting: `pyproject.toml` declares `Development Status :: 3 - Alpha`, but the README makes no maturity statement at all — someone installing it has no signal that it's alpha. And there's a `ci.yml` workflow with no corresponding CI status badge among the four badges.

I'll stop gathering now and let the agents finish rather than duplicate their work.

The PDF text extraction failed but the files were saved locally. Let me extract them directly.

`Operating System :: POSIX` — so no Windows support, which the README never states. Waiting on the agents now.

I have enough independent ground truth. Pausing here until the four research agents report back — I'll synthesize their findings with what I've verified and write the report.

`pdftotext` is available. Let me extract the real text from all four PDFs.

Now I have the real text. Let me extract the category frequency tables and results.

Table 3 captured — this is the core data. Let me get the classifier details plus threats to validity, and extract the other two PDFs.

Let me extract the actual correlation numbers from Venigalla & Chimalakonda, and the Liu et al. Java README study.

Art of README gives a concrete ordering that conflicts with standard-readme — a key disagreement. Now the CNCF materials.

Liu et al. gives me a large-n structural study. Let me now pull its specific numbers and open the remaining threads.

The `identify` output was noisy (per-frame). Let me get clean dimensions and verify links.

All eight repos opened successfully — no skips. Let me gather metrics and outlines.

Now let me extract the heading outlines and the above-the-fold content for each.

Found real peer-reviewable work on AGENTS.md — and note the marketing blogs spun it in the opposite direction. Let me fetch the actual papers.

Two agent-context papers with apparently divergent findings — worth reconciling. Let me get Gloaguen's detailed numbers and verify the Steinmacher "documentation is top barrier" claim, which I shouldn't assume.

Let me find an open-access version of the Steinmacher SLR and pursue the remaining threads.

Key correction emerging: the "documentation is the top barrier" premise may not hold. Let me verify against primary sources.

Let me get the Steinmacher SLR primary text plus two more directly relevant studies.

All README relative links resolve. Let me verify the docs site deployment, platform/requirements claims, and CI matrix.

Let me verify which assets are actually tracked in git (relative README paths only render on GitHub if committed).

Let me check the docs site liveness and README iteration cadence.

Let me locate the remaining two papers' full texts.

New lead on README/CONTRIBUTING introduction. Let me fetch that and keep hunting the Steinmacher SLR full text.

Research complete. Here are the notes.

---

# Canonical Guidance: Top-Level README.md for GitHub OSS Projects

## Method note

Repo-hosted specs (`standard-readme`, `awesome-readme`, `art-of-readme`, `cncf/project-template`, `cncf/techdocs`) were read from local checkouts opened via `/sase_repo` rather than web-fetched, so the quotes below are from source files, not rendered pages. Local paths given per source.

---

## 1. GitHub official docs

### 1a. About READMEs
<https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes>

**Prescribes no section list.** It prescribes five *questions* to answer:
- "What the project does"
- "Why the project is useful"
- "How users can get started with the project"
- "Where users can get help with your project"
- "Who maintains and contributes to the project"

**Mechanical rules (these are the actually-normative part):**
- Resolution order for auto-display: `.github/` → repository root → `docs/`. First hit wins.
- Relative links auto-rewrite per branch — use `docs/CONTRIBUTING.md`, not absolute URLs.
- GitHub auto-generates a TOC from Markdown headings; every heading gets an anchor.
- Scope limit, verbatim: **"A README should only contain information necessary for developers to get started using and contributing to your project. Longer documentation is best suited for wikis."**

That last sentence is the single strongest *named-source* backing for the "README routes, docs site manuals" position.

### 1b. Community profile / community standards
<https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/about-community-profiles-for-public-repositories>
<https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/accessing-a-projects-community-profile>

Checked items: **README, CODE_OF_CONDUCT, LICENSE, CONTRIBUTING, Issue templates, Pull request template, Security policy.**

Caveat worth flagging: I could **not** get the checklist enumerated verbatim with per-item descriptions off these pages — the docs describe the checklist's existence and link out, and the rendered checkmark list lives in the repo UI (`/community`), not in the docs prose. The item list above is assembled from scattered mentions across the two pages, not a single quoted block. Treat exact item naming as medium-confidence. The one item spelled out precisely: issue templates "must be located in the `.github/ISSUE_TEMPLATE` folder and contain valid `name:` and `about:` keys" (`.md`) or `name:`/`description:` (`.yml`) "to be displayed with a checkmark".

Note on your prompt: **"Communicating your project's needs" no longer exists** as a docs section — it was reorganized into "Setting up your project for healthy contributions" under Communities. Don't cite the old title.

### 1c. Community health files
<https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file>

Supported file types and purposes (verbatim where quoted):

| File | Purpose |
|---|---|
| `CODE_OF_CONDUCT.md` | "Defines standards for how to engage in a community" |
| `CONTRIBUTING.md` | "Communicates how people should contribute to your project" |
| `FUNDING.yml` | "Displays a sponsor button in your repository" |
| `GOVERNANCE.md` | project governance, roles, decision-making |
| `SECURITY.md` | "Gives instructions on how to report a security vulnerability" |
| `SUPPORT.md` | "Lets people know about ways to get help with your project" |
| Issue/PR templates + `config.yml` | "Customize and standardize the information you'd like contributors to include" |
| Discussion category forms | discussion templates |

Same `.github` → root → `docs` precedence. Org-wide defaults require a **public** `.github` repo.

**Design implication:** GitHub's own file taxonomy says support, security, governance, and contribution mechanics belong in *sibling files*, not in README. README links to them.

---

## 2. standard-readme (RichardLitt)

<https://github.com/RichardLitt/standard-readme/blob/main/spec.md>
Local: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/external/gh/RichardLitt/standard-readme/spec.md`

The most prescriptive source. **"Sections must appear in order given below. Optional sections may be omitted."**

### Full mandated ordering

| # | Section | Status |
|---|---|---|
| 1 | **Title** | Required |
| 2 | Banner | Optional |
| 3 | Badges | Optional |
| 4 | **Short Description** | Required |
| 5 | Long Description | Optional |
| 6 | **Table of Contents** | Required (optional if README < 100 lines) |
| 7 | Security | Optional |
| 8 | Background | Optional |
| 9 | **Install** | Required (optional for documentation repositories) |
| 10 | **Usage** | Required (optional for documentation repositories) |
| 11 | Extra Sections | Optional |
| 12 | API | Optional |
| 13 | Maintainer(s) | Optional |
| 14 | Thanks | Optional |
| 15 | **Contributing** | Required |
| 16 | **License** | Required — **"Must be last section"** |

### Per-section requirements (verbatim highlights)

- **Title** — "must match repository, folder and package manager names - or it may have another, relevant title with the repository, folder, and package manager title next to it in italics and in parentheses." Example: `# Standard Readme Style _(standard-readme)_`. Mismatch → must be explained in Long Description.
- **Banner** — "Must not have its own title." "Must link to local image in current repository." "Must appear directly after the title."
- **Badges** — "Must not have its own title." "Must be newline delimited." Suggests shields.io; suggests locally hosted static badges "to avoid external requests, which can result in tracking".
- **Short Description** — "Must not have its own title." "Must be less than 120 characters." "Must not start with `> `". "Must be on its own line." "Must match the description in the packager manager's `description` field." "Must match GitHub's description (if on GitHub)."
- **Table of Contents** — "Must link to all sections in the file." "Must start with the next section; do not include the title or Table of Contents headings." "Must be at least one-depth: must capture all level two headings."
- **Install** — "Code block illustrating how to install." Subsection `Dependencies` required if unusual/manual deps.
- **Usage** — "Code block illustrating common usage." Subsection `CLI` required if CLI functionality exists. If importable, code block showing "both import functionality and usage."
- **Extra Sections** — "This should not be called `Extra Sections`." Slot for 0+ titled sections, "placed after Usage and before API."
- **Maintainer(s)** — "Must be called `Maintainer` or `Maintainers`." Must include a contact method. "This should not be everyone with access rights, such as an entire organization."
- **Thanks** — "Must be called `Thanks`, `Credits` or `Acknowledgements`."
- **Contributing** — "State where users can ask questions." "State whether PRs are accepted." "List any requirements for contributing; for instance, having a sign-off on commits."
- **License** — "State license full name or identifier, as listed on the SPDX license list." "State license owner." "Must be last section."

### File-level requirements
- Named `README` with format extension (`.md`, `.org`, `.html`).
- i18n: `README.de.md` (BCP 47 tag). "Where there are multiple languages, `README.md` is reserved for English."
- Section titles must be translated for non-English READMEs.
- "Must not contain broken links."
- "If there are code examples, they should be linted in the same way as the code is linted in the rest of the project."

### Ordering rationale
The spec itself gives **no ordering rationale**. The rationale is imported from `README.md`'s Background section, which quotes perlmodstyle via Ken Williams:

> "Your documentation is complete when someone can use your module without ever having to look at its code… Remember: the documentation, not the code, defines what a module does."

and, on Long Description:

> "Ideally, someone who's slightly familiar with your module should be able to refresh their memory without hitting 'page down'. As your reader continues through the document, they should receive a progressively greater amount of knowledge." ~ Kirrily "Skud" Robert, perlmodstyle

Provenance: originated from a maxogden issue on `feross/standard`, formalized while maintaining the IPFS org's repos. Explicitly scoped: "Standard Readme is designed for open source libraries." **Not** designed for applications, services, or monorepos — relevant if you're evaluating it for a tool like sase.

---

## 3. Art of README (Stephen Whitmore / "hackergrrl" / Kira)

<https://github.com/hackergrrl/art-of-readme>
Local: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/external/gh/hackergrrl/art-of-readme/README.md`

This is the source `awesome-readme` lists first under Articles, and it **contradicts standard-readme on ordering**. Worth treating as a genuine second pole, not a footnote.

### The four jobs
> 1. tell them what it is (with context)
> 2. show them what it looks like in action
> 3. show them how they use it
> 4. tell them any other relevant details

### Prescribed ordering — "cognitive funneling"
1. **Name** — "self-explanatory names are best"
2. **One-liner**
3. **Usage** — "rather than starting to delve into the API docs, it'd be great to see what the module looks like in action"
4. **API** — "signatures, return types, callbacks, and events in detail. Types should be included where they aren't obvious. Caveats should be made clear."
5. **Installation** — "if I've read this far down, then I'm sold on trying out the module"
6. **License** — "most modules put this at the very bottom, but this might actually be better to have higher up… If you have a non-permissive license, stick it at the very top"

**The rationale is explicit and is the best-articulated ordering argument of any source:**

> "The ordering presented here is lovingly referred to as 'cognitive funneling,' and can be imagined as a funnel held upright, where the widest end contains the broadest more pertinent details, and moving deeper down into the funnel presents more specific details…"

> "the ordering of these key elements should be decided by how quickly they let someone 'short circuit' and bail on your module."

That last line is the actual decision procedure: **order sections by disqualification speed, not by workflow order.** Install is late because nobody installs before deciding.

### The README Checklist (verbatim)
- [ ] One-liner explaining the purpose of the module
- [ ] Necessary background context & links
- [ ] Potentially unfamiliar terms link to informative sources
- [ ] Clear, *runnable* example of usage
- [ ] Installation instructions
- [ ] Extensive API documentation
- [ ] Performs cognitive funneling
- [ ] Caveats and limitations mentioned up-front
- [ ] Doesn't rely on images to relay critical information
- [ ] License

### Notable positions
- **Brevity:** "The ideal README is as short as it can be without being any shorter. Detailed documentation is good -- make separate pages for it! -- but keep your README succinct."
- **Badges, skeptically:** "Be judicious in your use of badges. They're easy to abuse… They add visual noise to your README and generally only function if the user is reading your Markdown in a browser online… For each badge, consider: 'what real value is this badge providing to the typical viewer of this README?'"
- **Link rot:** "your version control repository and its embedded README will outlive your repository host and any of the things you hyperlink to -- especially images -- so *inline* anything that is essential."
- Usage example should exist as a runnable file in the repo (`example.js`).
- CLI projects: "show usage examples as command invocations and their output. If you create or modify a file, `cat` it to demonstrate the change before and after."

---

## 4. makeareadme.com

<https://www.makeareadme.com/>

Suggested sections, in its presented order:

1. **Name** — "Choose a self-explaining name for your project."
2. **Description** — what it does, context, links; optional subsections *Features*, *Background*
3. **Badges** — "Small images that convey metadata, such as whether or not all the tests are passing."
4. **Visuals** — screenshots or GIFs
5. **Installation**
6. **Usage** — "Use examples liberally, and show the expected output if you can."
7. **Support** — issue tracker, chat, email
8. **Roadmap**
9. **Contributing** — openness, setup steps, testing/linting procedures
10. **Authors and acknowledgment**
11. **License**
12. **Project status** — "Note if development has slowed or stopped; request maintainers if needed."

**Length stance, verbatim: "Too long is better than too short."** (Directly opposed to Art of README and GitHub — see §7.)

Unique contributions: **Visuals**, **Roadmap**, **Project status** as first-class sections. Project status in particular is not in any other source and is genuinely useful signal for abandoned-project detection.

---

## 5. Awesome README (matiassingers)

<https://github.com/matiassingers/awesome-readme>
Local: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/external/gh/matiassingers/awesome-readme/readme.md`

**Prescribes nothing.** It is a curated example list. Its only normative statement is:

> "Elements in beautiful READMEs include, but are not limited to: images, screenshots, GIFs, text formatting, etc."

Its value is as **revealed preference**: read the annotations across ~100 entries and the recurring praised elements are, in rough frequency order — project logo/banner, badges, clear one-line description, demo GIF or screenshot, TOC, feature list, simple install instructions, usage code samples, links for further reading, contributors section.

**Aesthetic bias worth naming:** the list rewards visual maximalism (logos, animated banners, emoji section icons, star-history charts, contributor avatar walls). This is close to the opposite of Art of README's advice and of GitHub's "only what's necessary to get started." If you cite awesome-readme as authority, you are citing a popularity aesthetic, not a spec.

Curated articles (§Articles) — these are the community's own canon pointer:
- "Art of Readme" — Stephen Whitmore
- "Elegant READMEs" — Yegor Bugayenko <https://www.yegor256.com/2019/04/23/elegant-readme.html>
- "How To Write A Great README" — thoughtbot <https://thoughtbot.com/blog/how-to-write-a-great-readme>
- "Readme Driven Development" — Tom Preston-Werner <https://tom.preston-werner.com/2010/08/23/readme-driven-development.html>
- "ARCHITECTURE.md" — Alex Kladov <https://matklad.github.io/2021/02/06/ARCHITECTURE.md.html>

---

## 6. Diátaxis — and an important negative finding

<https://diataxis.fr/> · <https://diataxis.fr/compass/> · <https://diataxis.fr/tutorials/> · <https://diataxis.fr/how-to-guides/> · <https://diataxis.fr/reference/> · <https://diataxis.fr/explanation/>

### Negative finding — read this first
**Diátaxis says nothing about READMEs.** I checked the site's page inventory and the four type pages; there is no README prescription, no "front door" framing, no guidance on README-vs-docs-site split. Diátaxis is a framework for organizing a *documentation corpus*. Any claim of the form "Diátaxis says a README should be X" is **not attributable** — it is an inference. I'm flagging this because that mapping circulates widely and looks sourced when it isn't.

### What it actually says

The compass (verbatim table):

| If the content… | …and serves the user's… | …then it must belong to… |
|---|---|---|
| informs action | acquisition of skill | a tutorial |
| informs action | application of skill | a how-to guide |
| informs cognition | application of skill | reference |
| informs cognition | acquisition of skill | explanation |

Two axes: **action vs. cognition**, and **acquisition vs. application** (equivalently practical/theoretical and study/work).

Definitions, verbatim:
- **Tutorial** — "A tutorial is an *experience* that takes place under the guidance of a tutor. A tutorial is always **learning-oriented**." / "A tutorial in other words is a lesson." / "*A tutorial is not the place for explanation.*"
- **How-to guide** — "How-to guides are directions that guide the reader through a problem or towards a result. How-to guides are goal-oriented." Recipe analogy; "it is not the responsibility of a recipe to teach you how to make something."
- **Reference** — "Reference guides are **technical descriptions** of the machinery and how to operate it. Reference material is **information-oriented**." Rule: "Describe and only describe." Map analogy: "A map tells you what you need to know about the territory, without having to go out and check the territory for yourself."
- **Explanation** — "Explanation is a discursive treatment of a subject, that permits *reflection*. Explanation is **understanding-oriented**." Analogy: McGee's *On Food and Cooking*.

Author: Daniele Procida.

### The defensible inference (labeled as mine, not Diátaxis's)
A README is not one of the four types; it is a **routing surface over all four**. What it legitimately holds is the irreducible minimum of each — enough explanation to answer "what/why", one how-to (install + first run), one pointer each to tutorial and reference. Every source that touches scope independently converges on this, but only GitHub states it as a rule ("Longer documentation is best suited for wikis"), and CNCF states the adjacent rule ("Does the documentation separate conceptual, instructional, and reference information?" — §7 of their criteria). Diátaxis is the *vocabulary* for that argument, not the source of it.

---

## 7. Checklists and maturity rubrics

### JOSS review checklist
<https://joss.readthedocs.io/en/latest/review_checklist.html>

Documentation section, verbatim:
1. **Statement of need:** "Do the authors clearly state what problems the software is designed to solve and who the target audience is?"
2. **Installation instructions:** "Is there a clearly-stated list of dependencies? Ideally these should be handled with an automated package management solution."
3. **Example usage:** "Do the authors include examples of how to use the software (ideally to solve real-world analysis problems)?"
4. **Functionality documentation:** "Is the core functionality of the software documented to a satisfactory level (e.g., API method documentation)?"
5. **Automated tests:** "Are there automated tests or manual steps described so that the functionality of the software can be verified?"
6. **Community guidelines:** "Are there clear guidelines for third parties wishing to 1) Contribute to the software 2) Report issues or problems with the software 3) Seek support"

This is the only source that makes **"Statement of need"** a named, first-class, reviewable artifact. It's the sharpest framing of the "what problem / for whom" opening.

### opensource.guide (published by GitHub, *not* Mozilla)
<https://opensource.guide/starting-a-project/>

README should answer:
- "What does this project do?"
- "Why is this project useful?"
- "How do I get started?"
- "Where can I get more help, if I need it?"

"Every project should include the following documentation": **open source license**, **README**, **contributing guidelines**, **code of conduct**.

Attribution correction for your prompt: opensource.guide is a **GitHub** property. There is no equivalent canonical *Mozilla* README rubric that I could find — Mozilla's open-source materials (MOSS, Mozilla Science Lab working-open guides) don't contain a README section spec. **Treat "Mozilla README guidance" as non-existent** unless you have a specific artifact in mind.

### CNCF README template
<https://github.com/cncf/project-template/blob/main/README-template.md>
Local: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/external/gh/cncf/project-template/README-template.md`

Prescribed section order:
1. `# Welcome to the [Projectname] Project!`
2. Mission statement paragraph — "[PROJECTNAME] is a [Type of Tool] that [Functions it performs]. [Reasons why these are needed and valuable]. [Implementation, strategy and architecture]."
3. Foundation attribution — "hosted by the Cloud Native Computing Foundation (CNCF)"
4. **Getting Started** — "quick installation/build instructions", "a few simple examples of use", "basic prerequisites"
5. **Contributing** — links to CONTRIBUTING.md
6. **Scope** — with **In Scope** and **Out of Scope** subsections
7. **Communications** — User Mailing List, Developer Mailing List, Slack Channel, Public Meeting Schedule and Links, Social Media, Other
8. **Resources** — roadmap, docs, website
9. **License**
10. **Conduct**

**Unique and genuinely distinctive: the explicit `Out of Scope` section.** No other source has this. For a governance-heavy or multi-stakeholder project it's the highest-leverage section on the list — it prevents the most expensive category of contributor misunderstanding. Sibling files in the template confirm the "README routes" model: `GOVERNANCE.md`, `MAINTAINERS.md`, `CONTRIBUTOR_LADDER.md`, `REVIEWING.md`, `DESIGN-PROPOSALS.md`, `CODE_OF_CONDUCT.md`, `SECURITY` all live outside README.

### CNCF TechDocs assessment criteria
<https://github.com/cncf/techdocs/blob/main/docs/analysis/criteria.md>
Local: `.../external/gh/cncf/techdocs/docs/analysis/criteria.md`

Scope caveat: this rubric grades **docs sites**, not READMEs. Relevant transferable items:
- "Does the documentation separate conceptual, instructional, and reference information?" (Diátaxis-adjacent, independently arrived at)
- "Is 'getting started' clearly labeled? ('Getting started', 'Installation', 'First steps', or the equivalent.)"
- "Is the 'happy path' — the most common use case — documented?"
- "Is there easily copy-pastable sample code or other example content?"
- "Do users know where to go after reading the getting started guide?"
- "If the documentation does not suffice, is there a clear escalation path for users needing more help?"
- Inclusive language: flags Inclusive Naming Initiative violations, and — notably — "Does the project use language like 'simple', 'easy', etc.?"

Maturity gating (cumulative): **Sandbox** = rudimentary docs or placeholder acceptable, may link out. **Incubating** = personas identified and their doc needs documented; docs hosted on the website; single-source requirement met; "comprehensive, addressing most stakeholder needs." **Graduated** = "fully addresses the needs of key stakeholders." **Archived** = archived status obvious via prominent banner; links to successor.

---

## 8. Where the sources actually disagree

| Question | Position A | Position B |
|---|---|---|
| **Install before or after Usage?** | **Install first** — standard-readme (9→10), makeareadme (5→6), CNCF (Getting Started bundles install first) | **Usage/API first, Install 5th** — Art of README: "if I've read this far down, then I'm sold on trying out the module" |
| **License placement** | **"Must be last section"** — standard-readme (hard requirement) | **"might actually be better to have higher up"**; non-permissive → "stick it at the very top" — Art of README |
| **Length** | **"Too long is better than too short."** — makeareadme | **"as short as it can be without being any shorter"** — Art of README; **"only… information necessary for developers to get started"** — GitHub |
| **Badges** | Section #3, unquestioned — makeareadme; celebrated throughout — awesome-readme | **"visual noise… easy to abuse"**, justify each one — Art of README. standard-readme is neutral-optional but warns of tracking via external badge hosts |
| **Images/GIFs** | **Visuals** = section #4 — makeareadme; logos/banners/GIFs praised in nearly every awesome-readme entry | **"Doesn't rely on images to relay critical information"**; inline essentials because hosts outlive links — Art of README |
| **Manual TOC** | **Required** unless <100 lines — standard-readme | Redundant in practice — GitHub auto-generates a heading TOC. Not a stated disagreement; an unacknowledged obsolescence. standard-readme's rule predates the feature |
| **Contributing in README** | **Required section** — standard-readme | Separate `CONTRIBUTING.md` — GitHub health files, opensource.guide, CNCF (README carries only a link) |
| **Maintainers in README** | Optional section — standard-readme | Separate `MAINTAINERS.md` — CNCF |
| **Roadmap / Project status** | Sections #8 and #12 — makeareadme (only source) | Absent from standard-readme, Art of README, GitHub |
| **Scope / Out of Scope** | Required — CNCF (only source) | Absent everywhere else |
| **Statement of need as named artifact** | Reviewable checklist item — JOSS (only source) | Others fold it into "description" |

**The load-bearing disagreement** is Install-vs-Usage, and it's not arbitrary — it's a disagreement about *reader model*. standard-readme/makeareadme order by **workflow** (you install, then you use). Art of README orders by **disqualification speed** (you decide, then you install). For a library discovered via package search, Art of README's model is better calibrated. For a tool a reader arrived at already intending to use, workflow order is fine. Pick based on how readers reach the project.

**Second-order tension:** standard-readme is the only source with machine-checkable MUSTs, which is why it's cited as *the* spec — but it self-scopes to "open source libraries" and its Node/npm heritage shows (title-matches-package-name, description-matches-`package.json`). Several of its hard requirements are inapplicable to applications, CLIs, and monorepos.

---

## 9. Attribution ledger

**Backed by a named source:**
- The five README questions → GitHub, About READMEs
- README scope limit / "longer documentation is best suited for wikis" → GitHub, About READMEs
- `.github` → root → `docs` precedence → GitHub, About READMEs + health files
- Full 16-section ordering with MUST/SHOULD levels → standard-readme spec.md
- 120-char short description, must match package manager + GitHub description → standard-readme
- License must be last → standard-readme
- TOC required above 100 lines, must capture all `##` → standard-readme
- Cognitive funneling; order by bail-out speed → Art of README
- Usage-before-Install; License possibly at top → Art of README
- 10-item README checklist → Art of README
- Badge skepticism; inline essential images → Art of README
- 12-section list incl. Visuals/Roadmap/Project status → makeareadme.com
- "Too long is better than too short" → makeareadme.com
- Four documentation types, compass table, per-type definitions → diataxis.fr
- Statement of need / installation / example usage / functionality docs / automated tests / community guidelines → JOSS
- License + README + contributing + code of conduct as the universal four → opensource.guide
- In Scope / Out of Scope; Communications channel list → CNCF project-template
- Separate conceptual/instructional/reference; happy path; escalation path; maturity gating → CNCF techdocs criteria

**Folk wisdom — could not attribute to any canonical source:**
- **"README is the front door."** Appears only in blog posts and vendor content (Atomic Object, Archbee, assorted dev blogs). Not in GitHub docs, standard-readme, Art of README, makeareadme, or Diátaxis. Rhetorically useful, but do not cite it as sourced.
- **"README routes, docs site manuals"** as an explicit doctrine. The *closest* named backing is GitHub's wikis sentence and Art of README's "make separate pages for it". Nobody states the routing principle as such.
- **Diátaxis-to-README mapping** (README = minimal slice of each of the four types). My inference. Diátaxis does not discuss READMEs at all.
- **"Above the fold" README advice.** Widespread; unattributable. The nearest real ancestor is perlmodstyle's "without hitting 'page down'", quoted secondhand by both standard-readme and Art of README.
- **Optimal README length figures** (e.g. "under 500 lines"). No source states a number. standard-readme's 100-line TOC threshold is the only numeric line-count rule in any canonical source, and it's about TOCs, not total length.

**Attribution corrections to your prompt's premises:**
- "Communicating your project's needs" — retired GitHub docs section title; now "Setting up your project for healthy contributions".
- "Mozilla/Open Source Guides" — conflates two things. opensource.guide is GitHub's. No canonical Mozilla README rubric appears to exist.
- awesome-readme is not guidance; it's a gallery with a visual-maximalist bias that runs against GitHub's and Art of README's scope advice.

Let me verify the Gaughan sample size (the "4,226" looks suspiciously like it echoes Prana's number) and extract the Steinmacher chapter text properly.

The canonical-guidance agent returned excellent material — including a genuinely valuable negative finding: **Diátaxis says nothing about READMEs**, so the common "README as front door per Diátaxis" framing is unattributable folk wisdom. It also surfaced a real disagreement between sources on Install-vs-Usage ordering that turns on reader model. Waiting on the remaining three agents.

Confirmed Gaughan's n=4226 is genuine (coincidental with Prana's 4,226 sections). Let me extract the Steinmacher documentation section in full.

I'll hold here until the empirical-literature, peer-teardown, and repo-audit agents report.

The "documentation is the top barrier" claim likely traces to the GitHub Open Source Survey, not Steinmacher. Let me verify that and check two more 2026 papers.

Let me verify the GitHub survey figure against its primary source and extract the factorial study.

I have complete ground truth. Here is the audit.

---

# README Audit — sase (workspace `sase_15`, master @ `d98b28462`)

## 1. README.md: outline, size

**File:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/README.md`
**109 lines · 552 words · 5.2 KB**

Exact heading outline (in order):

| Line | Heading |
| --- | --- |
| 3 | `# sase` (H1, inside `<div align="center">`) |
| 20 | `## Why sase` |
| 30 | `## See it in action` |
| 47 | `## Quick start` |
| 63 | `## Works with your agents` |
| 73 | `## Learn more` |
| 86 | `## Development` |
| 100 | `## Acknowledgements` |
| 107 | `## License` |

Structure: centered header block (tagline, 4 badges, `sase_overview.png` hero) → one-paragraph positioning statement → 5 bullet "Why" → 3 GIF demos with captions → quick start (4 commands) → agent support table (5 rows) → 8 doc links → dev setup → acknowledgements → license.

Badges present: Docs (sase.sh), PyPI version, PyPI pyversions, License MIT. **No CI status badge.**

## 2. Top-level docs inventory

| File | Lines | Covers | Linked from README? |
| --- | --- | --- | --- |
| `INSTALL.md` | 161 | uv tool install, prereqs table, plugin install, updates, required/optional system commands, uninstall | **Yes** (line 60) |
| `CONTRIBUTING.md` | 59 | setup, `just` workflow, deps, running tests, tox multi-version, lint ignores, `bd` beads issue tracking | **No — orphan** |
| `CHANGELOG.md` | 1158 | release-please generated, Unreleased + v0.10.2 back | **No** |
| `LICENSE` | 21 | MIT, Copyright (c) 2026 Bryan Bugyi | **Yes** (line 109) |
| `AGENTS.md` | 197 | agent instruction shim (Tier1/Tier2 memory). Mirrored as `CLAUDE.md`, `GEMINI.md`, `OPENCODE.md`, `QWEN.md` (all 12k) | **No** (by design) |
| `mkdocs.yml` | 125 | docs site config | n/a |

**`CONTRIBUTING.md` is referenced by nothing in the repo** — not README, not any `docs/*.md`, not `mkdocs.yml` nav. Verified via `grep -rn "CONTRIBUTING" README.md docs/*.md mkdocs.yml` → zero hits.

### docs/ directory
**63 markdown pages** (plus images/CSS/JS/templates). Top-level pages: `ace, acknowledgements, agent_families, agent_images, agent_providers, architecture, axe, beads, change_spec, cli, commit_workflows, configuration, content_layout, development, editor, fakey, getting_started, index, init, integrations, llms, memory, mentors, mobile_gateway, mobile_mvp_runbook, notifications, perf_runbook, plugins, project_spec, prompt, query_language, rust_backend, sdd, sdd_storage, telemetry, vcs, workflow_spec, workspace, xprompt`, plus `troubleshooting/{agent-revival,runner-slots}.md` and `blog/` (index + **10 posts**).

### mkdocs.yml nav (what sase.sh contains)
`site_url: https://sase.sh/`, `strict: true`, Material theme, Cloudflare Worker deploy (`wrangler.jsonc`, assets from `site/`).

- **Home:** index
- **Getting Started:** Your First 15 Minutes · Initialization · Content Layout Migration · Agent Providers
- **The Basics:** Memory · ACE TUI · AXE Automation · Spec-Driven Development · SDD Storage · XPrompts · Prompt History
- **Beyond the Basics:** Architecture · ChangeSpecs · Beads · Workflows · Agent Families · Workspaces · Mentors
- **The Nitty Gritty:** Commit Workflows · Notifications · Mobile Gateway · Mobile MVP Runbook · Performance Runbook · Telemetry · Agent Revival Log · Runner Slot Waits
- **Integrations:** Editor Integration · Integration APIs · Plugins · Fakey Testing Provider · LLM Providers · VCS Providers · Rust Backend
- **Reference:** CLI Reference · Development · Configuration · Query Language · ProjectSpec · Agent Attachments · Acknowledgements
- **Blog:** Blog Home

~40 nav entries; **README links 8 of them.** Not surfaced by README: the entire Blog (10 posts), Architecture, Memory, Beads, Workspaces, Mentors, Configuration, Commit Workflows, Rust Backend, Notifications, Editor Integration, and the **PDF handbook** (`/downloads/sase-handbook.pdf`, built + smoke-tested in `docs-deploy.yml`, linked from `docs/index.md` hero).

## 3. demos/out/ — GIF sizes and dimensions

All GIFs are **1920x1080**. All tracked in git.

| File | Size (bytes) | Size | Frames | In README? |
| --- | --- | --- | --- | --- |
| `sase_ace_multi_model_fanout.gif` | 3,839,067 | **3.7 MiB** | 789 | **Yes** |
| `sase_ace_prompt_history_stash.gif` | 1,655,767 | 1.6 MiB | 570 | No |
| `sase_ace_prompt_input.gif` | 1,362,404 | 1.3 MiB | 721 | No |
| `sase_ace_prs_pipeline.gif` | 1,065,956 | 1.1 MiB | 658 | **Yes** |
| `sase_ace_agents_observability.gif` | 774,035 | 756 KiB | 503 | **Yes** |

**README references 3 of the 5 existing GIFs.** No GIF exceeds GitHub's ~10 MB limit; largest is 3.7 MiB. **Combined README GIF payload = 5,679,058 bytes (5.4 MiB)**; adding the `sase_overview.png` hero (1.3 MiB) gives **~6.7 MiB of images on initial README load**. All three are displayed at `width="830"` while shipping 1920px-wide sources.

A **`.mp4` twin exists for every GIF** and is 1.5–2.7x smaller (`multi_model_fanout.mp4` = 1.4 MiB vs 3.7 MiB GIF; `prs_pipeline.mp4` = 677 KiB vs 1.1 MiB). Also `demos/out/last_generated_date.txt` (20 B, tracked). Tapes live in `demos/tapes/`, seed script in `demos/scripts/seed_sase_ace_demo`, and `demos/README.md` exists.

## 4. docs/images/

| File | Size | Dimensions |
| --- | --- | --- |
| `sase_overview.png` | 1.3 MiB | 1672x941 (**README hero**) |
| `sase-telegram-integration.png` | 1.6 MiB | 1672x941 |
| `sase-component-communication.png` | 1.5 MiB | 1672x941 |
| `bead-epic-work-infographic.png` | 1.3 MiB | 1672x941 |
| `sase-rust-core-integration.png` | 1.3 MiB | 1672x941 |
| `zorg-zettel-vision-infographic.png` | 1.3 MiB | 1672x941 |
| `xprompt-resolution-infographic.png` | 1.3 MiB | 1672x941 |
| `workflow-execution-infographic.png` | 1.3 MiB | 1672x941 |
| `sase_tui_tabs_infographic.png` | 1.1 MiB | 1672x941 |
| `sase_paper.png` | 739 KiB | 900x491 |
| `pdl_paper.png` | 635 KiB | 900x491 |
| `rust-backend-boundary-infographic.png` | 403 KiB | 1600x900 |
| `commit-workflow-infographic.png` | 141 KiB | 1672x941 |

Each infographic ships with `.prompt.md` and `.critique.md` sidecars. **Only `sase_overview.png` is used by README.**

`docs/images/blog/` holds **downscaled duplicates of the same demos** — `sase_ace_agents_observability.gif` (458 KiB, 1280x720), `sase_ace_multi_model_fanout.gif` (1.7 MiB, 1200x675), `sase_ace_prompt_history_stash.gif` (1.1 MiB, 1280x720), `sase_ace_prompt_input.gif` (847 KiB, 1280x720), plus `agents_observability_still.png` (174 KiB). README uses the full-size `demos/out/` variants, not these.

## 5. Link verification — all relative paths resolve

Every relative link/image in README resolves to a real, **git-tracked** file:

```
OK: docs/images/sase_overview.png
OK: demos/out/sase_ace_multi_model_fanout.gif
OK: demos/out/sase_ace_agents_observability.gif
OK: demos/out/sase_ace_prs_pipeline.gif
OK: INSTALL.md
OK: LICENSE
OK: docs/acknowledgements.md
```

**Zero broken relative links.** All 15 non-badge absolute URLs are well-formed.

One structural note (fact, not defect): `pyproject.toml` sets `readme = "README.md"`, so this file is PyPI's long description. The 5 relative paths above (4 images + 3 doc links) do not resolve on PyPI, and `[tool.hatch.build.targets.sdist] only-include = ["src/sase"]` excludes `demos/` and `docs/` from the sdist.

## 6. Things the project HAS that the README does NOT mention

| Item | Exists? | In README? |
| --- | --- | --- |
| `CONTRIBUTING.md` | **Yes** | **No** — no Contributing section at all |
| `CHANGELOG.md` (1158 lines) | **Yes** | **No** |
| Blog (10 posts, RSS plugin) | **Yes** | **No** |
| PDF handbook (`/downloads/sase-handbook.pdf`) | **Yes** | **No** |
| CI status badge | 4 workflows exist | **No** badge |
| Status/maturity statement | `Development Status :: 3 - Alpha` in pyproject | **No** — README never says alpha/beta/production |
| Platform support | POSIX only (Linux x86_64/aarch64, macOS; **no Windows**) | **No** — README is silent |
| `git` requirement | **Required** per INSTALL.md | **No** — Quick start lists only Python/uv/agent CLI |
| Text editor requirement (`$EDITOR`→nvim→vim) | **Required** per INSTALL.md | **No** |
| Rust core (`sase-core-rs`, hard dep) | **Yes** | Only implicitly — `sase core health` appears in Development with no explanation |
| Optional tooling (gh, tmux, bat, fzf, rg, delta, pandoc, wkhtmltopdf/xelatex, pdftoppm, kitten, prettier, clipboard helper, pass, node/npm) | **Yes**, 13 entries in INSTALL.md | **No** |
| Expansion of the "SASE" acronym | "Structured Agentic Software Engineering" (pyproject description, mkdocs `site_description`, AGENTS.md) | **No** — README gives pronunciation ("sassy") but never states what SASE stands for |
| Beads/`bd` issue tracking | CONTRIBUTING.md documents it | **No** |

## 7. Missing entirely (verified absent)

- **`SECURITY.md`** — absent at root and `.github/`
- **`CODE_OF_CONDUCT.md`** — absent at root and `.github/`
- **`.github/ISSUE_TEMPLATE`** — absent
- **`.github/PULL_REQUEST_TEMPLATE.md`** — absent

`.github/` contains **only workflows**: `ci.yml`, `docs-deploy.yml`, `pr-title.yml`, `publish.yml`.

## 8. pyproject.toml vs README claims

- **Name/version:** `sase` 0.10.2 · **Description:** "Structured Agentic Software Engineering"
- **requires-python:** `>=3.12` · **Classifiers:** Python 3.12/3.13/3.14, `Development Status :: 3 - Alpha`, `Operating System :: POSIX`, `Environment :: Console`, `Typing :: Typed`
- **Keywords:** agentic software engineering, automation, coding agents, developer tools, workflow orchestration
- **Runtime deps (14):** jinja2, jsonschema, packaging, pillow, pluggy, prometheus_client, pyinstrument, pyyaml, plotext, rich, ruamel.yaml, **sase-core-rs>=0.5.0,<0.6.0**, schedule, textual[syntax]
- **Extras:** dev, visual (pinned), terminal-smoke, docs, docs-pdf
- **`sase_llm` entry points (6):** agy, claude, codex, **fakey**, opencode, qwen
- **`sase_vcs`:** bare_git · **`sase_workspace`:** bare_git

**Claim-set match:** README's agent table (Claude Code, Antigravity `agy`, Codex, Qwen Code, OpenCode = 5) matches the 5 user-facing `sase_llm` entry points; `fakey` is the testing provider and is correctly omitted. README's "Python 3.12+" matches `requires-python`. **Mismatches/gaps:** README never states the Alpha maturity, never states POSIX-only/no-Windows, and never expands the acronym that is the package's own one-line description.

## 9. Git history — README.md

**270 commits total.** First: `a9a8ec70d` 2026-02-15 ("feat: Add project scaffolding and infrastructure (Phase 1)"). Latest: `ac92d6ade` **2026-07-17** ("docs: redesign README landing page").

By month: 2026-02 → 16 · 2026-03 → 55 · 2026-04 → 19 · 2026-05 → 91 · 2026-06 → 47 · 2026-07 → 42.

Very actively iterated. **The most recent commit (today) was a hard rewrite: 358 lines changed — 57 insertions, 301 deletions**, cutting the README from ~353 lines to its current 109. The current README is roughly one day old and is a deliberate slimming-down from a much longer document.

## 10. Docs site at sase.sh

**Deployed and live.** `docs-deploy.yml` builds on push to master (`just docs-check` → `just docs-pdf-check` → `just docs-deploy-artifact-check`) and deploys to a **Cloudflare Worker** (`wrangler.jsonc`, name `sase`, assets from `site/`), then smoke-tests `https://sase.sh/downloads/sase-handbook.pdf`.

**All 11 sase.sh URLs the README links return HTTP 200** (live check), and every one maps to a real page in `mkdocs.yml` nav:

| URL | HTTP | Nav source |
| --- | --- | --- |
| `https://sase.sh/` | 200 | `index.md` |
| `/getting_started/` | 200 | `getting_started.md` |
| `/agent_providers/` | 200 | `agent_providers.md` |
| `/ace/` | 200 | `ace.md` |
| `/xprompt/` | 200 | `xprompt.md` |
| `/change_spec/` | 200 | `change_spec.md` |
| `/axe/` | 200 | `axe.md` |
| `/sdd/` | 200 | `sdd.md` |
| `/plugins/` | 200 | `plugins.md` |
| `/cli/` | 200 | `cli.md` |
| `/development/` | 200 | `development.md` |

`use_directory_urls: true` + `strict: true` confirm the trailing-slash URL shape README uses is correct. `docs/_redirects` holds 4 legacy 301s.

---

## Summary of hard findings

1. **No broken links.** All 7 relative paths resolve and are git-tracked; all 11 sase.sh URLs return 200 and exist in nav.
2. **`CONTRIBUTING.md` is a complete orphan** — referenced by zero files in the repo.
3. **Four community-health files are absent:** SECURITY.md, CODE_OF_CONDUCT.md, issue templates, PR template.
4. **README image payload is ~6.7 MiB** (5.4 MiB across 3 GIFs + 1.3 MiB PNG); no single file breaches GitHub's ~10 MB limit. Smaller 1280x720 GIF variants and 1.5–2.7x smaller MP4 twins of the same demos already exist in-repo but are unused by README.
5. **README omits the project's own maturity (Alpha), platform constraint (POSIX/no Windows), the `git` and `$EDITOR` requirements, and the expansion of "SASE".**
6. **README surfaces 8 of ~40 doc pages**; the blog (10 posts) and the PDF handbook are entirely unsurfaced.
7. **README was rewritten today** (`ac92d6ade`, -301/+57), so its current shape is one day old and deliberately minimal — many omissions above are recent deletions, not long-standing neglect.

Let me find the referenced survey of agent context files and nail down Venigalla's specific results.

All 8 repos opened and analyzed — no skips.

# README Structural Teardown: 8 Developer-Tool Peers

All repos read from local checkouts under `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_15/sase/repos/external/gh/`.

## Size table (sorted)

| Repo | Lines | Words | Bytes | Code fences | Demo media |
|---|---|---|---|---|---|
| `block/goose` | 63 | 276 | 3.4K | 1 | none |
| `All-Hands-AI/OpenHands` | 150 | 903 | 8.5K | 4 | 2 PNG |
| `Aider-AI/aider` | 180 | 1,156 | 12K | 1 | 1 screencast SVG + 8 icon SVGs |
| `astral-sh/uv` | 326 | 1,080 | 9.9K | 16 | 1 benchmark SVG |
| `charmbracelet/bubbletea` | 402 | 1,910 | 15K | 9 | 2 GIF, 1 PNG |
| `BurntSushi/ripgrep` | 541 | 2,874 | 22K | 31 | 2 PNG |
| `astral-sh/ruff` | 563 | 2,021 | 25K | 13 | 1 benchmark SVG |
| `jesseduffield/lazygit` | 637 | 3,646 | 38K | 30 | **15 GIF** + ~106 PNG (mostly sponsor avatars) |

Word counts include inline HTML, so they overstate prose by ~15-30% for the HTML-heavy ones (aider, lazygit, OpenHands).

---

## 1. astral-sh/uv — the closest structural model

**Outline:** `# uv` → `## Highlights` → `## Installation` → `## Documentation` → `## Features` (`### Projects`, `### Scripts`, `### Tools`, `### Python versions`, `### The pip interface`) → `## Contributing` → `## FAQ` (`#### How do you pronounce uv?`, `#### How should I stylize uv?`, `#### What platforms does uv support?`, `#### Is uv ready for production?`) → `## Acknowledgements` → `## License`

**Above the fold:** No logo. `# uv` on line 1; 3 badges (PyPI version, Python versions, Discord); one-sentence tagline on line 7 — *"An extremely fast Python package and project manager, written in Rust."*; then a centered `<picture>` benchmark bar chart with dark/light `prefers-color-scheme` variants and an italic caption *"Installing Trio's dependencies with a warm cache."*; then `## Highlights` bullets. **No install command above the fold** — it's at line 44.

**Install:** Inline, ~30 lines, four fences (curl/sh, PowerShell, `pip install uv`, `pipx install uv`), plus `uv self update`, then routes out: *"See the [installation documentation](...) for details and alternative installation methods."* Deliberately shows only the top 4 paths.

**Demo:** No GIF. A generated benchmark chart doing the work a demo GIF would — the value prop is speed, so the "demo" is a bar chart.

**Docs routing:** Dedicated `## Documentation` section, 3 lines: docs site URL + *"the command line reference documentation can be viewed with `uv help`."* Every `### Feature` subsection ends with a "See the [X documentation]" link. README is a **funnel**, not a manual.

**Worth stealing:**
- The `## Highlights` bullet list where each bullet deep-links to either an in-README anchor (`#projects`, `#scripts`) or the docs site. It's a hybrid ToC/value-prop list.
- Feature subsections built from **real terminal transcripts** in ```` ```console ```` fences showing `$ uv init` → `$ uv add ruff` → `$ uv run` with actual output. No prose describing behavior — the transcript is the description.
- The FAQ answering *identity* questions (pronunciation, stylization, production-readiness) rather than troubleshooting.
- `<picture>` with `prefers-color-scheme` so the chart works in both GitHub themes.

## 2. astral-sh/ruff

**Outline:** `# Ruff` → `## Testimonials` → `## Table of Contents` → `## Getting Started` (`### Installation`, `### Usage`, `### Configuration`) → `## Rules` → `## Contributing` → `## Support` → `## Acknowledgements` → `## Who's Using Ruff?` (`### Show Your Support`) → `## License`

**Above the fold:** `# Ruff` (line 3); 6 badges; a text nav line `[**Docs**](https://docs.astral.sh/ruff/) | [**Playground**](https://play.ruff.rs/)`; tagline *"An extremely fast Python linter and code formatter, written in Rust."*; benchmark `<picture>` + caption *"Linting the CPython codebase from scratch."*; then emoji feature bullets (⚡️ 🐍 🛠️ 🤝 ⚖️ 📦 🔧 📏 ⌨️ 🌎). Install is at line 120.

**Install:** Inline under `### Installation` — `uv tool install ruff@latest`, `pip`, `pipx`, standalone curl/PowerShell, version-pinned. More exhaustive than uv's.

**Demo:** Same benchmark-chart-as-demo as uv (shared house style).

**Docs routing:** `## Table of Contents` opens with *"For more, see the [documentation](https://docs.astral.sh/ruff/)."* — and that exact sentence repeats under `## Getting Started`. Deliberate repetition.

**Worth stealing:**
- **`<!-- Begin section: Overview -->` / `<!-- End section: Overview -->` markers** (lines 1/101, 312/331). The README is the *source of truth* that gets sliced and embedded into the docs site — one copy, two renderings. Solves README/docs drift structurally.
- `## Testimonials` placed at position #2, **before the ToC and before install**. Named quotes from Sebastián Ramírez (FastAPI) etc. Social proof before mechanics.
- The prose "Ruff can be used to replace X, Y, Z" list — explicit incumbent displacement.
- `Ruff is backed by [Astral]` cross-linking sibling projects (uv's README does the mirror-image link).

## 3. Aider-AI/aider — closest domain peer

**Outline:** (no h1 markdown; HTML `<h1 align="center">`) → `## Features` with 9 doc-linked subsections: `### [Cloud and local LLMs]`, `### [Maps your codebase]`, `### [100+ code languages]`, `### [Git integration]`, `### [Use in your IDE]`, `### [Images & web pages]`, `### [Voice-to-code]`, `### [Linting & testing]`, `### [Copy/paste to web chat]` → `## Getting Started` → `## More Information` (`### Documentation`, `### Community & Resources`) → `## Kind Words From Users`

**Above the fold:** Centered logo SVG (width 300) → `<h1 align="center">AI Pair Programming in Your Terminal</h1>` — **the h1 is the tagline, not the project name** → one-line description → centered `screencast.svg` (an asciinema-style SVG, not a GIF) → 5 badges. No install above the fold (line 103).

**Install:** Minimal, one fence:
```bash
python -m pip install aider-install
aider-install
```
then `cd`, then three `aider --model X --api-key Y=<key>` variants for DeepSeek / Sonnet / o3-mini. Then routes out. **Note the multi-model shortcut list** — for an agent tool, "which model?" is answered in the install block itself.

**Demo:** SVG screencast directly under the tagline, above badges. SVG (not GIF) means crisp text at any zoom and much smaller files.

**Docs routing:** Aggressively out. Every `###` feature heading *is a link* to `aider.chat/docs/...`. Plus `## More Information` with two curated link lists. Almost nothing documented inline.

**Worth stealing:**
- **Headings-as-links.** `### [Git integration](https://aider.chat/docs/git.html)` — the outline doubles as the docs nav.
- **32×32 `align="left"` icon SVG per feature block** — each feature gets an icon floated left of 2-3 lines of text. Cheap visual rhythm without a GIF per feature.
- **Cog-generated badges** (`<!--[[[cog ... ]]]-->` / `<!--[[[end]]]-->` calling `scripts.homepage.get_badges_md()`) — live stats like `📦 Installs 6.8M`, `📈 Tokens/week 15B`, `🏆 OpenRouter Top 20`, and `🔄 Singularity 88%` (percent of the last release written by aider itself). Custom-metric badges beating generic CI badges.
- `## Kind Words From Users` as the **closer** — italic quotes with attribution links.

## 4. jesseduffield/lazygit — the demo-GIF exemplar

**Outline:** `## Sponsors` → `## Elevator Pitch` → `## Table of contents` → `## Features` (14 subsections) → `## Tutorials` → `## Installation` (**24 package-manager subsections**) → `## Usage` (`### Keybindings`, `### Changing Directory On Exit`, `### Undo/Redo`) → `## Configuration` (`### Custom Pagers`, `### Custom Commands`, `### Git flow support`) → `## Contributing` (`### Debugging Locally`) → `## Donate` → `## FAQ` (`### What do the commit colors represent?`) → `## Shameless Plug` → `## Alternatives`

**Above the fold:** **Lines 1-37 are paid sponsor banners** (Warp, Tuple, Subble). The actual project doesn't appear until line ~40: logo PNG, tagline *"A simple terminal UI for git commands"*, 7 badges, then `commit_and_push-compressed.gif` at ~line 52.

**Install:** Everything inline. 24 subsections from `### Homebrew` to `### Void Linux`, `### Funtoo Linux`, `### Termux`, `### Flox`. Opens with a repology `vertical-allrepos` badge (auto-updating package matrix) and a joke disclaimer about vetting third-party maintainers.

**Demo:** **The best-in-class pattern.** Hero GIF above the fold, then **one GIF per feature**, 15 total. Each `### Feature` block is: heading → 1-3 sentences that **name the exact keypress** → GIF. E.g. `### Cherry-pick`: *"Press `shift+c` on a commit to copy it and press `shift+v` to paste (cherry-pick) it."* → `![cherry_pick](../assets/demo/cherry_pick-compressed.gif)`. All named `*-compressed.gif` — compression is a deliberate, systematized step. Files live in `assets/demo/` and are **generated by an integration-test harness**, not hand-recorded.

**Docs routing:** Repo-local `docs/` (`/docs/keybindings`, `docs/Config.md`, `docs/Undoing.md`, `docs/Custom_Command_Keybindings.md`), no docs site. Sections often collapse to *"See the [docs](docs/Custom_Pagers.md)"* — one line, no inline duplication.

**Worth stealing:**
- The **feature block triple**: heading / keypress-level instruction / GIF. For a TUI this is the single highest-leverage pattern — it teaches the keymap and demos the feature simultaneously.
- `## Elevator Pitch` — a first-person rant naming the pain (*"Interactive rebasing requires you to edit a goddamn TODO file in your editor? Are you kidding me?"*). Wildly non-corporate, extremely memorable, and it earns the reader's identification before any feature list.
- `## Alternatives` — links competitors. Signals confidence.
- Repology badge instead of hand-maintained package matrix.

**Anti-pattern:** 37 lines of sponsor logos before the project name.

## 5. charmbracelet/bubbletea

**Outline:** `# Bubble Tea` → `## By the way` → `## Tutorial` (`### Enough! Let's get to it.`, `### The Model`) → `## Initialization` (`### The Update Method`, `### The View Method`, `### All Together Now`) → `## What's Next?` → `## Debugging` (`### Debugging with Delve`, `### Logging Stuff`) → `## Libraries we use with Bubble Tea` → `## Bubble Tea in the Wild` (`### Staff favourites`, `### In Industry`, `### Charm stuff`, `### There's so much more where that came from`) → `## Contributing` → `## Feedback` → `## Acknowledgments` → `## License`

**Above the fold:** `# Bubble Tea`; logo image (width 350) + 3 badges in one `<p>`; tagline *"The fun, functional and stateful way to build terminal apps."*; example GIF at line ~15 (full width); a "in production" paragraph listing perf features; a routing paragraph; a `> [!TIP]` callout for the v2 upgrade guide — *"point your LLM at it and let it go to town."*

**Install:** **None.** It's a Go library — `go get` is assumed. Instead the reader goes straight into a tutorial.

**Demo:** Hero GIF under the tagline; a second GIF in `## By the way` demoing the sibling `Bubbles` library.

**Docs routing:** Reference docs to pkg.go.dev; the README **is** the tutorial (~200 lines building a complete program incrementally). Then `## What's Next?` hands off to the commands tutorial + examples dir.

**Worth stealing:**
- `## Bubble Tea in the Wild` opening with *"There are over [18,000 applications](https://github.com/charmbracelet/bubbletea/network/dependents) built with Bubble Tea!"* — **the link is to GitHub's own dependents graph**, so the social proof is self-updating and unfakeable. Segmented into `### Staff favourites` / `### In Industry` (with company attribution: "Microsoft Azure – Aztify", "NVIDIA – container-canary") / `### Charm stuff`.
- `### There's so much more where that came from` inviting PRs to the list — turns social proof into a contribution ramp.
- The `> [!TIP]` GitHub callout for version migration.
- Reference link definitions (`[elm]`, `[docs]`, `[examples]`) at the bottom of each section — keeps prose readable in raw markdown.

## 6. BurntSushi/ripgrep — the classic

**Outline:** `ripgrep (rg)` (setext-style, `------` underline) → `### CHANGELOG` → `### Documentation quick links` → `### Screenshot of search results` → `### Quick examples comparing tools` → `### Why should I use ripgrep?` → `### Why shouldn't I use ripgrep?` → `### Is it really faster than everything else?` → `### Feature comparison` → `### Playground` → `### Installation` → `### Building` → `### Running tests` → `### Related tools` → `### Vulnerability reporting` → `### Translations`

Note: **flat — all `###`, no `##` at all**, and no h1 markdown heading.

**Above the fold:** **Prose first.** No logo, no centered anything. Lines 3-9 are a dense description paragraph that answers what/how/where in one breath. *Then* 3 badges (line 11), then the license line. Screenshot doesn't appear until line 34.

**Install:** Everything inline, ~215 lines (233-450), the longest install section here. Prose-driven rather than heading-driven: *"If you're a **macOS Homebrew** or a **Linuxbrew** user, then you can install ripgrep from homebrew-core:"* → fence. Bolded platform names carry the scanning load instead of subheadings.

**Demo:** One static PNG screenshot linking to the full-size image. No GIF — search output is static, so a screenshot suffices.

**Docs routing:** Repo-local companion files: `GUIDE.md`, `FAQ.md`, `CHANGELOG.md`. `### Documentation quick links` is a 8-item bullet list at line 22 — a hand-built nav bar pointing at both in-README anchors and sibling files, deep-linking to specific sections (`GUIDE.md#configuration-file`, `FAQ.md#complete`).

**Worth stealing:**
- **`### Why shouldn't I use ripgrep?`** — an honest anti-sell section. Enormous credibility purchase for near-zero cost.
- Benchmark **tables**, not charts: `| Tool | Command | Line count | Time |` with real commands and relative multipliers (`0.082s (1.00x)` ... `2.935s (35.94x)`), and the caveat *"Please remember that a single benchmark is never enough!"* linking to a detailed blog post.
- `### Documentation quick links` placed at the very top — the reader's escape hatch before the wall of prose.
- `### Related tools` and `### Translations` — ecosystem citizenship.

## 7. All-Hands-AI/OpenHands — agent-orchestration peer

**Outline:** (HTML header) → `## Quickstart` (`### Option 1: Without a Sandbox`, `### Option 2: With a Docker Sandbox`, `### Option 3: From Source`) → `# Architecture` → `## More documentation`

**Above the fold:** `<a name="readme-top">` anchor; centered logo (340px); `<strong>` tagline *"The self-hosted developer control center for coding agents and automations."*; sub-tagline *"Run OpenHands, Claude Code, Codex, Gemini, or any ACP-compatible agent across local, remote, and cloud backends."*; 5 `style=for-the-badge` badges; a **pipe-separated nav bar** (`Quickstart | Docs | Self-Hosting | ACP Agents | Automations | Slack`); full-width screenshot PNG; `<hr>`.

**Install:** Three labeled `### Option N` paths, each with an explicit **Prerequisites** line and `> [!WARNING]` callouts on the unsandboxed ones. Then a shared `---` + *"Access the UI at http://localhost:8000."*

**Demo:** Static PNG above the fold; a second architecture screenshot under `# Architecture`.

**Docs routing:** Almost everything to `docs.openhands.dev`. `## More documentation` is a 4-item list mixing external docs, an in-README anchor (`#architecture`), and a repo file (`./Development.md`).

**Worth stealing:**
- The **two-column feature table** — left cell is a bolded doc link, right cell is one benefit sentence:
  ```
  | [**Self-host your way**](...) | Run agents locally, in Docker, on VMs, or anywhere you can run an agent server backend |
  | [**Bring your own model**](...) | Use with any LLM |
  ```
  Much denser than bullets and forces one-sentence discipline.
- The **sub-tagline naming interoperable competitors** ("Claude Code, Codex, Gemini") — positions as orchestrator-above-agents rather than yet-another-agent. Directly relevant to an agent-orchestration project.
- `### Option 1/2/3` install framing with per-option Prerequisites + risk callouts.
- Note the heading-level inconsistency (`## Quickstart` then `# Architecture`) — sloppy, don't copy.

## 8. block/goose — the minimalist

**Outline:** `# goose` → `# Get started` → `# Quick links` → `## Need help?` → `# a little goose humor 🪿` → `# goose around with us`

**Above the fold:** `<div align="center">`; `# goose`; italic tagline *"your native open source AI agent — desktop app, CLI, and API — for code, workflows, and everything in between"*; 5 badges incl. an LF Insights health score and a repology packaging badge; a Trendshift badge (250×55); then 4 prose paragraphs. **`# Get started` at line 31 — install is the only thing near the fold.**

**Install:** Bolded desktop-app download link first, then *"Or install the CLI:"* + a single curl fence. That's it — everything else goes to `goose-docs.ai`.

**Demo:** **None.** No GIF, no screenshot. Notable gap given it ships a desktop app.

**Docs routing:** Total delegation. `# Quick links` is 6 links (Quickstart, Installation, Tutorials, Documentation, Governance, Custom Distributions); `## Need help?` is 2 troubleshooting links.

**Worth stealing:**
- Proof that **63 lines can be enough** when a docs site carries the load. The README is a landing page: what it is, how to start, where to go.
- The tagline packing surface area into one line — *"desktop app, CLI, and API"*.
- The prose paragraph that quantifies ecosystem: *"goose works with 15+ providers — Anthropic, OpenAI, Google, Ollama... Connect to 70+ extensions via the [Model Context Protocol]."* Numbers + name-drops.
- `# a little goose humor 🪿` — a genuine joke as a section. Cheap personality.

---

## Synthesis

### Common across ≥6 of 8

1. **Name + one-sentence tagline within the first 15 lines.** 8/8. The tagline formula is `<superlative> <category>, <differentiator>`: uv's *"An extremely fast Python package and project manager, written in Rust"*; ruff's *"An extremely fast Python linter and code formatter, written in Rust"*; lazygit's *"A simple terminal UI for git commands"*; bubbletea's *"The fun, functional and stateful way to build terminal apps"*. Never a paragraph. Never a mission statement.
2. **Badges immediately after the title, before any prose.** 8/8. 3-8 badges. The consistent set is version/registry + license + CI + chat. ripgrep is the only one that puts prose *before* badges.
3. **A visual within the first ~50 lines.** 7/8 (goose is the sole exception). The medium tracks the value prop: speed → benchmark chart (uv, ruff); interaction → GIF (lazygit, bubbletea); output → screenshot (ripgrep); UI → screenshot (OpenHands, aider).
4. **Install is inline, minimal, and links out for the rest.** 6/8. uv, ruff, aider, goose, OpenHands all show the 1-4 dominant paths in copy-pasteable fences, then say some version of *"See the installation documentation for alternative methods."* Only lazygit and ripgrep inline the exhaustive matrix — both are old, both distribute binaries through dozens of OS package managers, and both are worse for it.
5. **Features as a scannable list, each item deep-linked.** 8/8. Three variants: emoji bullets (ruff), anchor-linked bullets (uv `## Highlights`), heading-per-feature (aider, lazygit), two-column table (OpenHands).
6. **A separate docs site owns the reference material; README is a funnel.** 6/8 have one (docs.astral.sh, aider.chat, goose-docs.ai, docs.openhands.dev). The 2 without (lazygit, ripgrep) use repo-local `docs/`, `GUIDE.md`, `FAQ.md` — same pattern, different hosting. **Nobody documents comprehensively in the README.** The one apparent exception (bubbletea's inline tutorial) is a *library* whose README-as-tutorial substitutes for a getting-started page.
7. **Social proof as a named section.** 6/8. `## Testimonials` + `## Who's Using Ruff?` (ruff), `## Kind Words From Users` (aider), `## Bubble Tea in the Wild` (bubbletea), `## Sponsors` (lazygit), Trendshift badge (goose), `...and [many more]` project list (ruff). Position varies wildly: ruff puts testimonials at **#2**, aider puts them **last**.
8. **Terminal-native artifacts, never photos or mockups.** Console transcripts (uv), asciinema SVG (aider), recorded GIFs (lazygit, bubbletea), terminal screenshots (ripgrep).

### Idiosyncratic (one-offs worth noting)

- **ruff's `<!-- Begin section: X -->` markers** — README as docs-site source. Unique here, and the only *structural* solution to README/docs drift.
- **aider's cog-generated badges** — live custom metrics (`Installs 6.8M`, `Tokens/week 15B`, `Singularity 88%`) instead of generic CI badges. The "Singularity" badge (% of the release written by the tool itself) is the single most on-brand badge in this set.
- **lazygit's `## Elevator Pitch`** — a profane first-person rant. No other peer does emotional positioning.
- **ripgrep's `### Why shouldn't I use ripgrep?`** — the only explicit anti-sell.
- **uv's `## FAQ`** answering pronunciation and stylization — identity questions, not support questions.
- **goose's `# a little goose humor 🪿`** — an actual joke as a section.
- **OpenHands' two-column feature table** — the only one; also the densest feature presentation here.
- **bubbletea's dependents-graph link** as self-updating social proof.
- **lazygit's `## Alternatives`** — the only one linking competitors.

### The three archetypes

| | Length | Model |
|---|---|---|
| **Landing page** | 60-200 lines | goose, OpenHands, aider. Tagline + demo + minimal install + link list. Requires a docs site. |
| **Funnel** | 300-560 lines | **uv**, ruff. Tagline + chart + highlights + install + per-feature transcript with a "see the docs" link each. Convinces *and* routes. |
| **Manual** | 540-640 lines | lazygit, ripgrep. Exhaustive install + full feature tour. Bloat is almost entirely the package-manager matrix. |

### Most relevant recommendations for a Python/uv-installable CLI+TUI that orchestrates AI coding agents

The project sits at the intersection of uv (Python/uv-installable), lazygit (TUI), and aider/OpenHands (agent domain). The synthesis:

1. **Take uv's skeleton**, since it's the same distribution channel: `# name` → badges → tagline → visual → `## Highlights` (anchor-linked) → `## Installation` (uv/uvx/pipx only, then link out) → `## Documentation` → `## Features` (transcript per feature, each ending in a docs link) → `## Contributing` → `## FAQ` → `## License`.
2. **Take lazygit's feature-block triple** for the TUI half — heading / exact-keypress sentence / GIF, with GIFs generated from the test harness and named `*-compressed.gif`. This is the highest-value pattern in the whole set and the one uv can't provide (uv has no TUI, so it has no demo).
3. **Take OpenHands' sub-tagline** — name the agents it orchestrates (Claude, Codex, Gemini) in the second line. For an orchestrator, "works with the agent you already use" is the positioning, and OpenHands is the only peer that puts it above the fold.
4. **Take aider's headings-as-links** if there's a docs site, or ripgrep's `### Documentation quick links` block if docs stay in-repo.
5. **Take ripgrep's `### Why shouldn't I use X?`** — cheapest credibility available.
6. **Don't inline an install matrix.** uv-installable means `uv tool install` / `uvx` / `pipx` and nothing else belongs in the README.
7. **Don't ship without a demo.** goose is the only peer with no visual, and it's conspicuous.

The audit returned a finding that reframes everything: **the README was rewritten today** (commit `ac92d6ade`, −301/+57), deliberately cutting it from ~353 lines to 109. So many "omissions" are recent, intentional deletions — my recommendations need to respect that minimalist intent rather than argue for re-bloating it.

Other hard findings: `CONTRIBUTING.md` is referenced by zero files in the repo, all links resolve (nothing broken), and the README never expands its own acronym or states that it's Alpha and POSIX-only. Waiting on the last two agents.

Let me fetch the "Agent READMEs" study — the direct analogue of Prana for agent context files.

The peer teardown is very strong. Key calibration: at 109 lines, sase's README is squarely in the **"landing page" archetype** alongside goose (63), OpenHands (150), and aider (180) — which is exactly right for a project with a ~40-page docs site. That plus today's deliberate slimming means recommendations should sharpen the landing page, not push it toward the 560-line "funnel" shape.

Waiting on the last agent (empirical literature), then I'll write the report.

I'll hold for the final agent before synthesizing.

Let me confirm the eye-tracking gap and get Prana's per-category classifier numbers.

One last check — the user explicitly asked about llms.txt, and I should not report a gap without looking.

I have enough to report rigorously. Here are the findings.

---

# GitHub READMEs: Empirical & Academic Literature

## Scope note on rigor

Three of your five premises needed correction against primary sources. I've flagged those inline rather than confirming them. Where I could not verify a claim, I say so. All PDFs below were text-extracted and read directly (not summarized from abstracts) except where noted.

---

## 1. Prana, Treude et al. — the anchor paper ✅ verified, with two corrections

**Citation:** Prana, G.A.A., Treude, C., Thung, F., Atapattu, T., Lo, D. "Categorizing the Content of GitHub README Files." *Empirical Software Engineering* 24, 1296–1327 (2019). [DOI 10.1007/s10664-018-9660-3](https://link.springer.com/article/10.1007/s10664-018-9660-3) · open preprint: [arXiv:1802.06997](https://arxiv.org/abs/1802.06997) (paywalled at Springer; I read the arXiv v2 full text)

### Correction 1: the 8th category is "Other", not "Status"

The taxonomy is **What, Why, How, When, Who, References, Contribution, Other**. There is no "Status" category — *status* content (project status, versions, roadmap) lives under **When**. Worth getting right if you're citing it.

### Correction 2: "commonly present vs. missing" is two different numbers

This is the single most important nuance in the paper, and it's easy to misreport. **Table 3**, verbatim:

| # | Category | # Sections (%) | # Files (%) |
|---|---|---|---|
| 1 | What | 707 (16.7%) | 381 (**97.0%**) |
| 2 | Why | 116 (2.7%) | 101 (**25.7%**) |
| 3 | How | 2,467 (**58.4%**) | 348 (**88.5%**) |
| 4 | When | 180 (4.3%) | 84 (**21.4%**) |
| 5 | Who | 322 (7.6%) | 208 (52.9%) |
| 6 | References | 858 (20.3%) | 239 (60.8%) |
| 7 | Contribution | 122 (2.9%) | 109 (27.8%) |
| 8 | Other | 58 (1.4%) | 27 (6.9%) |
| – | Exclusion | 696 | |

**The measured finding:** ~97% of READMEs say *what* the project is and 88.5% say *how* to use it, but only **25.7% say why it exists** and only **21.4% state project status**. So roughly **3 in 4 READMEs never answer "why should I care?" or "is this alive?"**

**The nuance that matters for your advising:** *What* appears in 97% of **files** but only 16.7% of **sections**. *How* dominates sections at 58.4%. Translation: the "What" is present but **thin** — typically one intro paragraph — while "How" sprawls. A README that is 58% install/config instructions and one line of "what" is the *statistical norm*, not a failure case.

### Methodology & caveats

- **Sampling:** random GitHub repo IDs (0–100M) via API. 1,193 repos inspected → **393 included**. Exclusions: software w/ README <2KB (429), non-software w/ large README (127), non-software + small (196), non-English (48).
- **Generalizability claim:** ±4.94 confidence interval at 95%, *assuming a population of 20M repos*. Note this is a 2018 sample — GitHub has grown ~10× since.
- **The <2KB filter is a real limitation for your use case:** it deliberately excludes the most minimal READMEs. The true "missing Why" rate across *all* GitHub is almost certainly worse than 74%.
- **Section structure:** median **7 sections** per README; 50% of files have 5–12.
- **Annotation:** open coding, 2 annotators (a PhD student + industry engineer, neither an author), ~30h each, **Cohen's Kappa = 0.858**; third annotator + majority vote for disagreements.
- **Repo type mix:** end-user apps 42%, libraries 27.9%, learning resources 17.4%, frameworks 7.3%, UI 5.4%. (Skews toward apps — a library-only sample might differ.)
- **Classifier:** multi-label, 8 categories, **F1 = 0.746**. Ablation: heuristic features only 0.584; statistical only 0.706.
- **Association rules (file level):** `{How} ⇒ {What}` support 0.86, confidence 0.97; `{What} ⇒ {How}` support 0.86, confidence 0.89.

### Measured vs. recommended — important

The 20-professional survey measured **perceived** usefulness of badge labels, not task performance. The authors explicitly flag this: *"we measured perceived usefulness of the visual labels... which may not correspond to actual usefulness in a software development task."* Any claim that Prana et al. *showed* better READMEs improve outcomes is **not supported** — they showed content distribution + a classifier + a perception survey. The paper's advice to repo owners is an **unmeasured recommendation**.

---

## 2. README structure/content vs. stars — three studies, converging on an awkward answer

### 2a. Liu, Noei & Lyons (2022) — largest sample, best statistics

**Citation:** Liu, Y., Noei, E., Lyons, K. "How README Files are Structured in Open Source Java Projects." *Information and Software Technology*. [PDF](https://enoei.github.io/papers/liu2022readme.pdf)

**Sample:** 14,901 Java repos (sampled from 142,471, 99% confidence level); **11,594 English READMEs**. Methods: Mann-Whitney, Cliff's delta, clustering, Kruskal–Wallis + Dunn's.

**Presence of GitHub-recommended sections, and effect size on stars:**

| Section | Present | p-value | Cliff's δ |
|---|---|---|---|
| Table of Contents | 177 (**2%**) | 5.69e-07 | 0.219 |
| Credits | 406 (**4%**) | 7.62e-23 | 0.287 |
| Contributing | 620 (**5%**) | 6.98e-68 | **0.415** |
| License | 1,471 (**13%**) | 5.56e-147 | **0.416** |
| Installation | 2,398 (**21%**) | 2.43e-122 | 0.311 |
| Usage | 3,615 (**31%**) | 1.50e-161 | 0.314 |
| Description | 4,730 (**41%**) | 3.07e-04 | **0.039** |

**The striking result:** the sections with the **largest** effect sizes (License 0.416, Contributing 0.415) are the **rarest** (13%, 5%). The most common section (Description, 41%) has a **negligible** effect (δ=0.039). Also: 32 clusters of README structures identified; **56.25% of clusters** differ significantly in star distribution — but the authors conclude *"the most frequent README file structures are associated with less popular repositories."*

**Caveat the authors themselves raise:** stars are a popularity proxy, and **causality is unestablished** — popular projects plausibly attract better documentation rather than the reverse. Java-only.

### 2b. Venigalla & Chimalakonda (2022)

**Citation:** [arXiv:2206.10772](https://arxiv.org/abs/2206.10772). ⚠️ Marked *"Manuscript submitted to ACM"* — I could **not** confirm peer-reviewed acceptance. (A possibly-related 2025 Venigalla paper exists in *Software: Practice and Experience*, [DOI 10.1002/spe.3390](https://onlinelibrary.wiley.com/doi/10.1002/spe.3390), which I did not verify.)

**Sample:** 1,950 READMEs across 10 languages. Fisher's exact test on Prana's categories (assigned via LDA):

- **Significant (p<0.05) across all 10 languages:** **What, References, Contribution**
- **Not significant for any language:** **Why, When**
- *How* significant only for C#; *Who* significant for all except Java.

**Caveats:** correlational; popularity groups are threshold-defined; LDA-based category assignment is noisy (weaker than Prana's human annotation).

### 2c. Gaughan, Champion, Hwang & Shaw (2025) — the causality check, and it's negative

**Citation:** "The Introduction of README and CONTRIBUTING Files in Open Source Software Development." CHASE 2025. [arXiv:2502.18440](https://arxiv.org/abs/2502.18440)

**Sample:** README **n=4,226**, CONTRIBUTING **n=714**, from Debian-packaged FLOSS (drawn from 21,902 Debian packages; 4,247 projects). *(The 4,226 is a genuine coincidence with Prana's 4,226 sections — I verified it against the abstract.)* Methods: multilevel time series, LDA, negative binomial regression.

**Measured:**
- README median publication: **same day as initial commit** (SD >3 years)
- CONTRIBUTING median: **1,806 days** (~4.9 years) into development
- **README median reading time: 14.79 seconds** (under 160 words) — READMEs are *short*
- CONTRIBUTING median reading time: 19.73s
- Docs get published **around local maxima in contribution activity**; weekly commit activity **declines** afterward

**The authors' explicit finding:** documentation **follows** activity rather than causing it, and they state there is *"no evidence to support such causality"* regarding documentation catalyzing growth. This directly contradicts the common advocacy claim (Mozilla/GitHub/Linux Foundation) that early community docs drive recruitment.

**Caveat:** Debian-packaged projects skew mature/packaged; analyzes only the **initial version** of each file.

### Synthesis for your project
Every star-correlation result here is **correlational**, and the one study that explicitly tested temporal direction found the arrow pointing the *wrong way*. Treat "good README → more stars" as **unproven**. The defensible claim is narrower: certain sections (license, contributing) co-occur with popular projects and are rare enough to be cheap differentiators.

---

## 3. Newcomer onboarding barriers — ⚠️ your premise is wrong

### Correction 3: Steinmacher does NOT find documentation is the top barrier

**Citations:**
- Steinmacher, I., Graciotto Silva, M.A., Gerosa, M.A. "Barriers Faced by Newcomers to Open Source Projects: A Systematic Review." OSS 2014, IFIP AICT 427, pp. 153–163. [PDF](https://www.ime.usp.br/~gerosa/papers/Steinmacher2014_Chapter_BarriersFacedByNewcomersToOpen.pdf) — **21 studies analyzed** (I read this full text)
- Steinmacher, I., Graciotto Silva, M.A., Gerosa, M.A., Redmiles, D.F. "A systematic literature review on the barriers faced by newcomers to open source software projects." *Information and Software Technology* 59:67–85 (2015). [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0950584914002390) — **291 studies retrieved from 4 digital libraries → 20 primary**. ⚠️ **Paywalled (HTTP 403); I could not read the full text.** Details below come from the 2014 conference version + abstract.

**Five barrier categories:** finding a way to start, social interactions, code issues, **documentation problems**, newcomers' previous experience/knowledge.

**Most-evidenced barriers (from the paper's own abstract):** *"newcomers' previous technical skills, receiving response from community, centrality of social contacts, and finding the appropriate way to start contributing."* **Documentation is not among them.** Socialization barriers are reported as most evidenced, appearing in **75% (15/20)** of studies.

**What the Documentation Problems category actually contains** (§3.4, read directly): only three sub-barriers — **Outdated Documentation**, **Information Overload**, and **Code Comments not Clear**. None concern README first impressions. The information-overload finding actually cuts *against* comprehensive docs: *"just providing a bunch of documentation leads to information overload."*

### Where the "documentation is the #1 barrier" claim actually comes from

**[GitHub Open Source Survey 2017](https://opensourcesurvey.org/2017/)** — verified against the primary source:

> *"Incomplete or outdated documentation is a pervasive problem, observed by **93% of respondents**, yet **60% of contributors** say they rarely or never contribute to documentation."*

Also measured: **64%** say an open source license is very important in deciding whether to **use** a project; **67%** in deciding whether to **contribute**.

**Methodology & caveats:** 5,500 randomly sampled respondents from 3,800+ OSS repos on GitHub.com, plus 500+ non-random from other platforms; sampled from repo traffic/activity, invited by dialog box. This is an **industry survey, not peer-reviewed**. Critically, 93% **"observed"** the problem — that measures *pervasiveness*, not severity ranking, and not whether it blocked anyone. Self-report, not behavioral.

**Nice convergence worth using:** GitHub's survey says license is the top-rated doc for both use (64%) and contribution (67%) decisions; Liu et al. independently found license had the **largest measured effect size on stars** (δ=0.416) while appearing in only **13%** of Java READMEs. Two different methods, same signal.

### Tangential: Steinmacher et al., "Almost There" (ICSE 2018)

[PDF](https://gustavopinto.org/lost+found/icse2018.pdf). 21 projects, surveys of 355 quasi-contributors + 21 integrators. Found 10,099 quasi-contributors (~70% of actual contributors), 12,367 non-accepted PRs. **19 reasons** for non-acceptance — but these are overwhelmingly about *PR review* (superseded/duplicated: 52 mentions; vision mismatch: 45; integrator disinterest: 25), **not documentation**. The closest hit: integrators ranked *"Guidelines not followed"* second (9 occurrences). **I would not cite this as README evidence.**

---

## 4. "Above the fold" for READMEs — ⚠️ no such study exists

**I could not find any eye-tracking or attention study of README files or developer docs landing pages.** Multiple search strategies returned nothing. I'm reporting this as a genuine gap rather than substituting a proxy and letting it read as evidence.

The best available data is **general web usability, not developer docs**:

**[NN/g, "Scrolling and Attention"](https://www.nngroup.com/articles/scrolling-and-attention/)** (Fessenden, 2018 update):
- **57%** of page-viewing time above the fold; **74%** in the first two screenfuls (to 2160px)
- 2010 predecessor study (1024×768): **80%** above the fold
- Sample: **130,000+ eye fixations, 120 participants**, 1920×1080
- **Pages studied: news, ecommerce, blogs, FAQs, encyclopedic content — no developer documentation, no READMEs**

**So: "above the fold matters for READMEs" is an extrapolation, not a measured finding.** It may well be true, but nobody has measured it. Two measured data points that bear on it indirectly:
- Gaughan et al.: median README reading time **14.79s** (<160 words) — for the *median* repo the fold problem may be less acute than assumed, since the whole file fits.
- Prana et al.: median **7 sections** per README — but the "What" occupies only 16.7% of sections, so what's above the fold is disproportionately *install instructions*, not orientation.

---

## 5. READMEs as context for LLM agents (2025–2026) — most relevant to your project

### 5a. "Agent READMEs" — the Prana-equivalent for context files

**Citation:** Chatlatanagulchai, W., Li, H., Kashiwa, Y., Reid, B., Thonglek, K., Leelaprute, P., Rungsawang, A., Manaskasemsak, B., Adams, B., Hassan, A.E., Iida, H. "Agent READMEs: An Empirical Study of Context Files for Agentic Coding." [arXiv:2511.12884](https://arxiv.org/abs/2511.12884) (Nov 2025). Kasetsart / Queen's / NAIST.

**Sample:** **2,303 context files from 1,925 repos** (≥5 stars): 922 Claude Code, 694 OpenAI Codex, 687 GitHub Copilot. Via AIDev dataset + GitHub API.

**Content prevalence:** Testing 75.0% · Implementation Details 69.9% · Architecture 67.7% · Development Process 63.3% · Build and Run 62.3% · System Overview 59.0% · Maintenance 43.7% · Config & Env 38.0% · Documentation 26.8% · AI Integration 24.4% · Debugging 24.4% · DevOps 18.1% · **Performance 14.5%** · **Security 14.5%** · UI/UX 8.7% · Project Management 5.4%

**Other measured:**
- Median length: Claude Code ~485–535 words; Codex 335.5 words
- Readability: Claude Code median **Flesch Reading Ease 16.6** ("very difficult"); Copilot 26.6; Codex 39.6
- Structure: shallow hierarchy, single H1, **median 6–7 H2 sections** — *a near-exact match for Prana's median 7 README sections*
- Maintenance: **67.4%** of Claude Code files have multiple commits; median update interval Claude 24.1h, Codex 22.0h, Copilot 70.7h; evolve via small incremental additions
- Their classifier: 0.79 micro-F1 (Architecture 0.93, Testing 0.94, Maintenance 0.56)

**Caveat:** purely **descriptive** — measures what's *in* the files, never whether they *work*. Sampling biased to ≥5-star repos; 3 tools only.

### 5b. Does AGENTS.md actually help? — evidence is mixed and early

**⚠️ Marketing-blog correction:** several SEO pages (augmentcode, morphllm, betterclaw, llms-txt.io) report this literature as *"developer-written context files help... ~4 percentage points."* That **cherry-picks one number and inverts the paper's conclusion.** Here's what the paper says.

**Citation:** Gloaguen, T., Mündler, N., Müller, M., Raychev, V., Vechev, M. "Evaluating AGENTS.md: Are Repository-Level Context Files Helpful for Coding Agents?" [arXiv:2602.11988](https://arxiv.org/abs/2602.11988) (Feb 2026, rev. Jun 2026). ETH Zurich SRI Lab / LogicStar.ai.

**Headline (authors' own words):** *"providing context files does not generally improve task success rates, while increasing inference cost by over 20% on average."*

- **AGENTbench:** 138 instances, 12 Python repos w/ developer-written context files. Plus SWE-bench Lite (300 tasks, 11 repos)
- **Agents:** Claude Code (Sonnet-4.5), Codex (GPT-5.2, GPT-5.1-mini), Qwen Code (Qwen3-30b-coder)
- **Results:** SWE-bench Lite, LLM-generated: **−0.5%**. AGENTbench: LLM-generated **−2%**, developer-written **+4%**. Cost: **+20–23%**, driven by increased tool interactions
- *"Repository overviews, although popular and recommended by model providers, are not helpful"* — context files don't meaningfully reduce steps before the agent reaches relevant files
- Removing documentation made LLM-generated files **outperform** developer versions by 2.7%
- Agents **did** follow instructions (more testing, broader exploration) — which made tasks *slower and harder*

**Caveats:** Python only; success-rate only; niche repos; **n=138** — the +4% is a small effect on a small sample, which is exactly why the authors don't headline it.

**Countervailing citation:** Lulla, J.L., Mohsenimofidi, S., Galster, M., Zhang, J.M., Baltes, S., **Treude, C.** "On the Impact of AGENTS.md Files on the Efficiency of AI Coding Agents." [arXiv:2601.20404](https://arxiv.org/html/2601.20404v2) (Jan 2026). *(Note: same Christoph Treude as the 2019 README paper — he's now studying the agent-facing version of the same question.)*

- 10 repos, 124 PRs, OpenAI Codex (gpt-5.2-codex), paired with/without AGENTS.md in Docker; PRs ≤100 LOC and ≤5 files
- Wall-clock median: **98.57s → 70.34s (≈28.64% faster)**; mean 162.94s → 129.91s (≈20.27%)
- Output tokens median: **2,925 → 2,440 (≈16.58% fewer)**; mean 5,744.81 → 4,591.46 (≈20.08%)

**Reconciling the apparent contradiction** (Gloaguen: +20% cost; Lulla: −20% tokens) — they measure different things and don't actually conflict:
- **Different tasks:** Gloaguen = SWE-bench-style bug fixing on niche repos; Lulla = reproducing small, well-scoped PRs (≤100 LOC)
- **Different metrics:** Gloaguen = total inference cost *including tool calls* + success rate; Lulla = wall-clock + output tokens only, **no correctness measure**
- **Different breadth:** Gloaguen = 3 agents/4 models; Lulla = Codex only, 10 repos
- Plausible read: AGENTS.md *narrows search* on small scoped tasks (Lulla's win) but *induces extra exploration/testing* on open-ended tasks (Gloaguen's cost). Both are small studies. **The honest summary is that the evidence is genuinely early and unsettled.**

### 5c. File structure may not matter at all — the most actionable finding for you

**Citation:** McMillan, D. "Instruction Adherence in Coding Agent Configuration Files: A Factorial Study of Four File-Structure Variables." [arXiv:2605.10039](https://arxiv.org/pdf/2605.10039). HxAI Australia. ⚠️ **Preprint, single author, industry lab, not peer-reviewed — weight accordingly.**

- **Scale:** 1,650 Claude Code CLI sessions, **16,050 function-level observations**, 2 TypeScript codebases, 3 models (Sonnet 4.6 primary; Opus 4.6 CLI-matched; Opus 4.7 descriptive under CLI-version confound), 5 tasks. Mixed-effects models + Bayesian companion.
- **Variables:** file size (25–500 lines), instruction position, file architecture (single vs. split), conflicting instructions.
- **Result: none of the four structural variables — nor three two-way interactions — produced a detectable contrast after multiple-testing correction.** Size and conflict nulls supported by **affirmative-null Bayes factors (BF10 0.05–0.10)**; position and architecture nulls are failures-to-reject *without* Bayes support (weaker).
- **Largest effect is within-session decay:** each additional generated function ≈**5.6% lower odds of compliance** (OR = 0.944); non-monotonic; **median first omission at generation position 4**.
- **Task identity beats file structure:** 26.2 percentage-point compliance gap between two tasks.

**Caveats:** the compliance target was a **trivial annotation** — may not generalize to substantive instructions. The within-session finding was **post-hoc, not pre-specified**. Preprint.

**Why this matters for an agent-orchestration tool:** if it holds, tuning AGENTS.md *length/position/structure* is low-yield, and compliance decays *within a session* regardless of the file. That argues for enforcement (hooks, linters, CI) over prose — which is what your repo's `just check` convention already does.

### 5d. llms.txt — no evidence found

**I found no peer-reviewed or preprint empirical study measuring llms.txt efficacy.** The only figure surfaced was an SEO vendor (SE Ranking) claiming a 10.13% adoption rate across 300k domains — an **adoption** stat, not efficacy, from a commercial source I did not verify against a primary methodology. Treat llms.txt as **evidence-free** at present.

### 5e. Unverified claims circulating that you should not repeat

- **"GitHub's engineering team analyzed 2,500+ repositories and found effective files prioritize copy-pasteable commands…"** (augmentcode.com, morphllm.com) — **I could not verify this exists.** It appears to be a garbled restatement of Chatlatanagulchai et al.'s 2,303 files / 1,925 repos, which is *not* GitHub's engineering team and reports no such finding.
- **AGENTS.md adoption: "60,000+ repos"** (llms-txt.io) vs. **"40,000-plus"** (McMillan citing agents.md). Both are vendor/advocacy figures; no independent measurement. Don't cite a precise number.

---

## Bottom line for an agent-orchestration tool

1. **The best-supported README finding is the Why/status gap** — 74.3% lack "Why", 78.6% lack status (Prana, n=393). That's a real, cheap differentiator, and it's measured.
2. **Don't claim READMEs drive adoption.** Every star correlation is confounded, and the only study testing temporal direction (Gaughan, CHASE 2025) found docs *follow* activity and explicitly reports no causal evidence.
3. **License + Contributing are the rare/high-effect-size sections** (δ≈0.416/0.415, present in 13%/5% — Liu, n=11,594 Java), and GitHub's survey independently ranks license #1 for both use and contribution decisions. Two methods, one signal.
4. **"Above the fold" for READMEs is unmeasured.** Argue it from first principles if you like, but don't dress it in NN/g's numbers — those are news and ecommerce pages.
5. **Agent context files are early-evidence territory.** The strongest current results are *deflationary*: repo overviews don't help (Gloaguen), file structure doesn't move adherence (McMillan), and security/performance appear in only 14.5% of real files (Chatlatanagulchai). If your tool's pitch involves agents consuming repo docs, the literature currently favors **enforcement over prose**.

**Access failures, for the record:** Springer (Prana published version), ScienceDirect (Steinmacher IST 2015 — the canonical version; I used the 2014 conference version + abstract instead), and ACM DL (Qiu et al. 2019 "Signals that Potential Contributors Look For", CSCW — could not obtain; it looks directly relevant to README-as-first-impression and is worth a library pull).

The final agent returned with real rigor — it corrected three of my framing premises rather than confirming them. Now I'll synthesize all four into the report.

Report written. Let me verify it landed cleanly.

The research is written to `sase/repos/research/202607/github_readme_best_practices.md` (508 lines), left uncommitted for your review.

## The headline finding

**Your README's shape is already right — don't let this research talk you into re-bloating it.** At 109 lines it sits in the "landing page" archetype next to goose (63), OpenHands (150), and aider (180), which is the correct form for a project with a ~40-page docs site. I found the 2026-07-17 rewrite (`ac92d6ade`, −301/+57) that cut it from ~353 lines, so what look like omissions are mostly deliberate deletions. The real gaps aren't missing sections — they're **missing facts**.

## Recommended changes, highest value first

1. **Link `CONTRIBUTING.md`** — it exists and is referenced by *zero files in the repo*. This is the best-evidenced item in the whole report: Contributing has the second-largest measured effect size on stars (δ=0.415) while appearing in only 5% of READMEs, and GitHub's 2017 survey independently ranks contribution guidance a top decision factor (67%). Two methods, one signal. One line fixes it.
2. **State that sase is Alpha.** `pyproject.toml` says `Development Status :: 3 - Alpha`; the README never mentions it. 78.6% of READMEs omit status — it's the most common gap in the corpus, and you currently have it.
3. **Expand the acronym.** The README gives the pronunciation ("sassy") but never says *Structured Agentic Software Engineering* — which is your own `pyproject` description.
4. **State POSIX-only + the `git`/`$EDITOR` requirements.** No Windows support, and Quick start omits two hard prerequisites that `INSTALL.md` lists.
5. **Fix PyPI rendering — this is a real defect, not style.** `readme = "README.md"` makes this your PyPI long description, PyPI doesn't rewrite relative URLs, and your sdist excludes `demos/` and `docs/`. All four images and three doc links render **broken on PyPI** right now, invisibly from GitHub.
6. **Cut the ~7.03 MB media payload.** The fix already exists in-repo, unused: `docs/images/blog/` has 1280×720 variants of the same demos (fan-out 1.7 MB vs 3.84 MB). Nothing needs regenerating.
7. **Add a CI badge** (four workflows, no status badge) and **surface the PDF handbook** — CI builds *and* smoke-tests it, `docs/index.md` features it, and the README never links it.

I explicitly recommend **against** a Table of Contents (standard-readme's >100-line rule predates GitHub's auto-TOC; only 2% of 11,594 Java READMEs have one) and against manufactured social proof while Alpha.

## Two things worth knowing about the evidence

I had the agents verify claims rather than confirm my framing, and **three of my starting premises were wrong**: Diátaxis says nothing whatsoever about READMEs (the "front door" framing is unattributable folk wisdom), Steinmacher does *not* find documentation is the top newcomer barrier (socialization is), and there is no eye-tracking study of READMEs at all — "above the fold" advice borrows NN/g numbers measured on news and ecommerce pages. Those corrections are flagged in the report.

Most importantly: **don't claim a good README drives adoption.** Every star correlation is confounded, and the one study testing temporal direction (CHASE 2025) found docs *follow* activity and states outright there's "no evidence to support such causality."

One tangential finding you may care about strategically: the agent-context-file literature is currently *deflationary* — ETH Zurich found repo overviews don't improve task success and cost +20% inference, and a factorial study found file size/position/structure had no detectable effect on adherence, with the dominant effect being within-session decay. If that holds, it favors **enforcement over prose** — which is what your `just check` convention already does.

I made this change — the research report is mine from this session. Let me commit it.

Confirmed: one untracked file, which is the report I wrote. Committing it now.

I'll record the skill use, then commit.

Repo convention is `docs(research):`. Writing the commit message now.

Clean and in sync with `origin/main`. One thing I want to check before reporting — there's a commit just below mine with a suspiciously similar name that wasn't in the log earlier.

Committed as `ebfc146` on `main`, pushed, working tree clean.

## What I did

Committed the research report to the `sase--research` sidecar as `docs(research): research README best practices for sase`, matching the repo's existing tag convention. The commit message summarizes the four research strands, the prioritized recommendations, and the three unsupported claims the report corrects.

## One thing worth flagging

The rebase pulled in a commit that landed while I was working: `782fbfb` "docs: research top-level README best practices" by agent `research.g.cdx`, adding `202607/github_top_level_readme_best_practices.md` (248 lines). **Another agent researched the same question in parallel and wrote a separate file.** There's no conflict — the filenames differ (`github_readme_best_practices.md` vs `github_top_level_readme_best_practices.md`), so both now sit side by side in `202607/`.

You likely want one, not two. I'd suggest either reading both and keeping the stronger one, or having me merge them — but I didn't want to delete or overwrite another agent's work without asking, especially since I haven't read it and can't yet say whether it covers ground mine misses.
