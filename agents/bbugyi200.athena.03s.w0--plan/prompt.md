#gh:gh_sase-org__sase We currently support completion for common words used in previous prompts via
the `<ctrl+t>` keymap, but that completion menu often doesn't sort its entries ideally.
Can you help me fix this by sortin common words by recency/frequency/relation with other
words in the prompt (in other words, words that were used in prompts containing other
words that already exist in the current prompt input widget should be prioritized)?

- Think hard about the smartest way to do this and make sure we prioritize recency /
  frequency / relation appropriately.
- Add some (visually appealing) signal as to why each word is prioritized the way it is
  in the completion menu where possible (without hurting performance).
- #beau 

#plan #m_opus 