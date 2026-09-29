- **PLAN:**
  [202609/prompt_next_word_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)
- **AGENTS:**
  - [bbugyi200.apollo.2x--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2x.md)

I want to add excellent "next-word" prediction for the very next word in the prompt
input widget using the user's / project's prompt history (and maybe just common
sense?--think hard about how to make this work). This would need to be fast and would be
triggered using `<ctrl+t>` after using `<ctrl+t><ctrl+t>` to complete the first /
selected word in the completion menu. This way they can just keep hitting `<ctrl+t>` if
the next-words that we guess are correct. Can you help me implement this? Review the
prompt_next_word_prediction.md file in the research sidecar repo for context and
inspiration before planning.

I want you to lead the design on this one. Make sure you design this feature so it is
intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly
and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.
