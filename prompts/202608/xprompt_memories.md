- **PLAN:**
  [202608/xprompt_memories.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_memories.md)
- **AGENTS:**
  - [bbugyi200.athena.vh.f3--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.vh.f3.md)

%xprompts_enabled:false

# Previous Conversation

**User:**

Can you help me start requiring that xprompt skills be defined in a sase/skills/
directory?

- Currently, these are defined in sase/xprompts/skills/ directories normally, but it is
  the `skill: true` frontmatter property that really controls whether an xprompt is an
  xprompt skill or not (I think at least--you should verify this).
- Also, let's start requiring that, in order to invoke these as xprompts (instead of as
  skills using the `/` prefix), that we include the `skills/` prefix (e.g. `#skills/foo`
  instead of `#foo`).
- Make sure you migrate all of my xprompt skills accordingly across all of my enabled
  sase projects and my chezmoi repo.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.

**Assistant:**

_Plan submitted for review._

**Plan file:** `/home/bryan/.sase/plans/202608/xprompt_skill_directories.md`

> # Plan: Canonical xprompt skill directories and namespaced invocation
>
> ## Context and verified current behavior
>
> The current classifier is the Markdown/config `skill` value, not the directory. Python
> parses the value directly into `XPrompt.skill`, and `select_skill_xprompts()` selects
> every truthy value. The native Rust catalog independently does the same truthiness
> check. The special packaged `src/sase/xprompts/skills/` directory is only an extra
> directory scanned by the built-in loader; its location does not itself establish the
> skill contract. Config-defined and plugin-defined xprompts can therefore become skills
> today without living in any skills directory. There is also one name serving two
> incompatible purposes today: `XPrompt.name` is both

_See full plan file for details._

---

%xprompts_enabled:true

# New Query

The previous agent's work has been implemented (see the sase-hb epic bead for more
context). Can you now help me make sase memories a special type of xprompt?

- These will be termed "xprompt memories". You should add a good (but concise) entry to
  the sase/memory/glossary.md xprompt memory file for this new term.
- In order to invoke these as xprompts, the `#memory/` prefix should be required.
- For example, in order to expand the sase/memory/glossary.md xprompt memory file's
  contents in a prompt, I should be able to use `#memory/glossary`.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
