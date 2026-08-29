#gh:gh_sase-org__sase Can you help me change some of the contents from the sase/memory/sase.md memory
file that gets generated? Namely, we should change the following text:

```
IMPORTANT REMINDERS:

- Do NOT locate, clone, or web-fetch another repo's contents any other way than by using
  `/sase_repo` or `sase artifact read`!
- The `sase artifact read <ref> "<reason>"` command MUST be used to read artifacts (so
  the reads are audited) from sidecar repos. Do NOT read sidecar artifact files
  directly.
```

This text should be changed to:

```
**IMPORTANT**: The `sase artifact read <ref> "<reason>"` command MUST be used to read
artifacts (so the reads are audited) from sidecar repos. Do NOT read sidecar artifact
files directly or locate, clone, or web-fetch another repo's contents any other way than
by using `/sase_repo` or `sase artifact read`!
```

#plan #m_opus