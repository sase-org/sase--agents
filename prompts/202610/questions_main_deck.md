- **PLAN:**
  [202610/questions_main_deck.md](https://github.com/sase-org/sase--plans/blob/main/202610/questions_main_deck.md)
- **AGENTS:**
  - [bbugyi200.athena.research.58.linker.w0--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.58.linker.w0.md)

I would like to start setting sase variables automatically whenever the /sase_questions
skill is used. The goal of this change is to make it so when the user selects an agent
session on the "Agents" tab that is associated with an agent turn that asked questions,
those questions, their recomended answers, their actual answers (if any questions have
been answered yet), and how the questions were answered (if any questions have been
answered yet) are all immediately visible (since variables are rendered in the main
deck). Can you help me implement this? Review the
question_answers_in_agents_main_deck.md file in the research sidecar repo for context
and inspiration before planning. I agree with all of the requirements recommended in
that research file (but keep in mind that you are responsible for planning and splitting
up this work appropriately).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
