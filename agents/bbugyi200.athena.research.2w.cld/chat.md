# Chat History - ace-run (research.2w.cld)

- **TIMESTAMP:** 2026-09-29 07:10:34 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2w.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260929_065034.md`

## Prompt

%id(cld, clan=research.2w)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.2w.cdx`, `research.2w.grk`, `research.2w.mus`, `research.2w.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to add
excellent support for bead file attachments.

- We already support leaving notes of the form `@<path_to_file>` as long as
  `@<path_to_file>` is the only contents of the note.
- We should add support for `@<path_to_file>` references anywhere in a note and require
  that `@@` be used if a literal `@` is needed.
- We should have robust (but optional--not all users will necessarily run the
  `sase bead show` command using a terminal that supports viewing images, for
  example--also I'm not sure that sase agents will want this enabled since it might be
  easier for them to use image file paths to read images directly) support for viewing
  images
- Finally, make sure that large and arbitrary binary files are supported. Think hard
  about the best way to add support for these.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

I'll start by exploring how bead notes and the existing `@<path>` note support work today.

Status: research is essentially complete. One last quantitative check — simulating my proposed grammar against the real note corpus so the report can cite exact breakage numbers.

I have everything I need. Writing the report now.

Now registering the report as a durable artifact snapshot.

I wrote the research report and registered it (`file:explicit:319caea68c74312bbdeb81d2`, label `research:202609/bead_note_file_attachments__cld.md`). The commit of the research repo is declared for the host to perform.

**Report:** `sase/repos/research/202609/bead_note_file_attachments__cld.md`

**Is it a good idea?** Yes. Notes already point at local evidence files by path, and those references rot. Of 94 such paths in bead text, 29 are already gone even on athena. None can be read from apollo or mac. Some point at files that keep changing, like `tui.log`. In one case, `sase-133.5.4` compared `/tmp/local.png` with `/tmp/apollo.png`, and both files are gone.

**Where I'd push back on the plan:**
1. **The existing `@path` does something else.** A note of exactly `@<path>` doesn't attach anything: it reads the note's *text* from that file. About ten CLI flags work this way. I'd keep that behavior as is, and add attachments as a separate rule about `@path` *inside* the note text.
2. **Requiring `@@` for every literal `@` breaks too much.** 7.7% of the 11,902 existing notes contain `@`, mostly mid-word: email-style author stamps, `claude@xhigh`, `repo@sha`. I propose a narrower rule:
   - `@` only matters at the start of a word, and only in front of something that looks like a path.
   - Code spans are ignored, `@kind:` references are left alone, and plain words like `@large` stay literal.
   - A path that doesn't exist fails the whole command loudly.
   - I ran this rule against the real notes: only **35 notes (0.29%)** would have needed an escape.
3. **Store a copy of the file, not its path, and keep the bytes out of the beads repo.** That repo is **public**, 140 MiB with 18k commits, and every bead write takes its lock.
4. **Images should be a `show`-only extra.** The existing `show` (humans) versus `read` (agents) split already fits. `read` should print real local paths that keep the file extension, so agents can open images directly.
5. **The plan is missing some pieces:**
   - a way to delete an accidentally attached secret
   - where the bytes live and who can see them
   - a single meaning of "attached" (`sase artifact create --bead` already attaches files, but only on one machine)

**Recommended solution:**
- **How notes store attachments.** Each note gets an optional list of its attachments (name, hash, size, type), and the note text shows a readable `@attachment:<name>`. This is a new optional field on the existing note event rather than a new event type. Older SASE versions ignore unknown fields but refuse unknown event types, so this doesn't break other machines, and no existing notes need migrating.
- **Where the bytes go.** A copy is kept locally in `~/.sase/attachments`. It is also uploaded to a **private `--attachments` git repo** (default cap 50 MiB per file; GitHub blocks at 100 MiB). Files over the cap go to an optional **`rclone` backend** — Cloudflare R2, or an SFTP folder on athena — up to 2 GiB.
- **Upload first, then write the note.** A crash can leave unused bytes behind, but never a note that points at missing bytes.
- **Viewing images.** `show --images auto` tries kitty graphics (tmux-safe), then iTerm2, then sixel, then SASE's existing half-block renderer (which works through the pager), then nothing. It also adds clickable file links. `sase bead attachment open` reuses the existing kitty artifact viewer.

The report also has mockups, a comparison of storage options (including why I'd avoid Git LFS: GitHub can't delete individual LFS objects), a four-phase rollout, and five open questions. The main ones for you: should the attachment store be private by default, and should large files go to athena over SFTP or to R2?
