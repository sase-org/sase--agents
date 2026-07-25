#gh:gh_sase-org__sase Can you help me fix the `sase init` command? If we detect an agent.md file in any directory, we should copy the contents of that file and create an equivalent for every LLM provider that is configured with sase, just like we do with the root directory. This is not happening today. See the below command output for evidence. Make sure we git commit these new files. #plan %a:tale

```
❯ sase init
SASE is initialized. No init subcommands need to run.
Checked: memory, sdd, skills.

bryan in 🌐 athena in sase on  master is 📦 v0.10.2 via  v22.14.0 via 🐍 v3.11.13
❯ tree demos
demos
├── casts
├── out
│   ├── last_generated_date.txt
│   ├── sase_ace_prompt_input.gif
│   └── sase_ace_prompt_input.mp4
├── README.md
├── scripts
│   └── seed_sase_ace_demo
└── tapes
    ├── AGENTS.md
    └── sase_ace_prompt_input.tape

5 directories, 7 files
```