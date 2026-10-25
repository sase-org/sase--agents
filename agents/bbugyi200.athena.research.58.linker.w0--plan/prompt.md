#gh:gh_sase-org__sase I would like to start setting sase variables automatically whenever the
/sase_questions skill is used. The goal of this change is to make it so when the user
selects an agent session on the "Agents" tab that is associated with an agent turn that
asked questions, those questions, their recomended answers, their actual answers (if any
questions have been answered yet), and how the questions were answered (if any questions
have been answered yet) are all immediately visible (since variables are rendered in the
main deck). Can you help me implement this? Review the question_answers_in_agents_main_deck.md file in the
research sidecar repo for context and inspiration before planning. I agree with all of
the requirements recommended in that research file (but keep in mind that you are
responsible for planning and splitting up this work appropriately).

#plan %m:@xlarge %w:research.58.linker %auto