# Changelog

## 1.1.0 — 2026-07-02

- **Quality floor upgrade:** correctness-critical findings (crash, data loss, security) must now be flagged in one line even when unasked — "suppress noise, never warnings." Verified: the trivial-question demo now carries the crash warning at half the baseline's answer size.
- **n=5 variance study** on the flagship review task: −63% mean output tokens (range −54% to −67%), both planted bugs found in 10/10 runs across both arms; volunteered-depth tradeoff documented honestly.
- Consistency fixes from external review: headline ranges now separate /eco from /eco-max; planted-vs-unplanted bug counts disclosed per arm; /eco-max's cache-key interaction documented; activation-cost number unified (~1.2k); compaction re-invoke caveat; uninstall instructions; sources added for all Anthropic claims; release tag re-pointed at a reachable commit.

## 1.0.0 — 2026-07-02

Initial public release.

- **`/eco`** — frugality rules with a non-negotiable quality floor: answer-first replies, no paste-backs of applied diffs, grep-first targeted reads, Edit-over-Write, batched tool calls, cheap Haiku delegation for broad sweeps, no unprompted progress recaps. Persists for the whole session from one invocation. Replies in the user's language.
- **`/eco-max`** — the same rules **plus** a low reasoning-effort override via skill frontmatter, for routine chores. Instructed to escalate honestly to `/eco` when a task turns out hard.
- **`/eco setup`** — proposes persistent savings in `settings.json` (`effortLevel: medium`, MCP output caps); applies only after explicit confirmation.
- **Benchmarks** — 23 headless runs across five task types (review, real edits, trivial question, multi-file 3-turn session, cross-model check on Opus/Sonnet/Haiku), raw JSONs included. Result: −48% to −75% output tokens at graded quality parity on frontier models, with fixes executed and verified — plus one published negative result (Haiku).
- **Harness** — `benchmarks/run.ps1` / `benchmarks/run.sh` for one-command A/B measurement of your own workload.
- **Guide** — `docs/token-optimization-guide.md`: every known token lever in Claude Code, ranked, with sources.
