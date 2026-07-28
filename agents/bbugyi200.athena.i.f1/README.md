# Agent: i.f1

[Agent Hoods](../../README.md) / [bbugyi200](../../users/bbugyi200/README.md) / [athena](../../users/bbugyi200/machines/athena/README.md) / [i](../../users/bbugyi200/machines/athena/hoods/i/README.md) / i.f1

**Global name:** `bbugyi200.athena.i.f1` · **State:** active · **Source run:** `run-0d89ededdd132485c1eb597c98881b7d`

**Owner:** `bbugyi200.athena` · **Project:** sase · **Hood:** i

## Summary

- Model: gpt-5.5
- Provider: codex
- Timing: 2026-07-06T19:41:44.851456+00:00
- Commits: 0
- Variables: [7](#variables)

## Files

[Chat](chat.md) · [Prompt](prompt.md)

## Variables

| Variable | Value |
|---|---|
| `completion_fix` | Make file completion visible by using a prefix with multiple candidates, such as @src/, or seed another parser-like file so @src/par opens a menu instead of auto-inserting parser.py. |
| `dirty_version_fix` | Clean or commit generated fake-workspace SDD files during hidden setup before launching ACE so the title bar does not show the distracting .dirty version suffix. |
| `gif_fix` | For GIF legibility, consider a GIF-oriented render with FontSize 22 and slightly less padding, or keep MP4 as the high-detail artifact and publish a shorter/cropped GIF focused on the prompt area. |
| `media_paths` | demos/out/sase\_ace\_prompt\_input.mp4; demos/out/sase\_ace\_prompt\_input.gif; demos/out/sase\_ace\_prompt\_input.png |
| `pacing_fix` | Increase dwell after #add\_tests, xprompt args, file completion, prompt stack, and submit modal from about 800ms to about 1.25-1.5s; keep the final modal around 2s for GIF scanning. |
| `review_status` | reviewed\_regenerated\_mp4\_and\_gif |
| `top_recommendation` | Move Show until after ACE has reached the Agents screen so the recording does not spend the first roughly 4 seconds on a mostly blank terminal/startup. |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [i](../../families/bbugyi200.athena.i.md) (family · 2) | ancestor | active 1, completed 1 |
