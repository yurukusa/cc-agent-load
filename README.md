# cc-agent-load

See how much of your Claude Code time is **you** vs **AI autonomous subagents**.

**Try it in your browser:** [yurukusa.github.io/cc-agent-load](https://yurukusa.github.io/cc-agent-load/)

```
npx cc-agent-load
```

## Sample output

```
  cc-agent-load
  ═════════════════════════════════════════════
  Scanning: ~/.claude/projects/

  ▸ Your Time vs AI Time

  You   ████████░░░░░░░░░░░░░░░░  41h (34%)  86 sessions
  AI    ████████████████░░░░░░░░  79h (66%)  3420 sessions

  ▸ AI Autonomy Ratio
  ████████ 1.9x  — AI ran 1.9x longer than you

  Your AI matches your pace.

  ▸ Top Projects (AI load)
  ~                     █████████░░░  90.6h total
  cc-loop               ███░░░░░░░░░  25.4h total

  ── Share ──
  My Claude Code AI load: 66% subagent / 34% me — 1.9x autonomy ratio
  npx cc-agent-load  #ClaudeCode #AIAutonomy
```

## What it tells you

When you run `cc-session-stats`, the session count includes every subagent spawned via the Task tool. This tool separates them:

| Metric | What it means |
|--------|---------------|
| **Your time** | Sessions where you were at the keyboard |
| **AI time** | Autonomous subagent sessions (Task tool spawns) |
| **Autonomy ratio** | How much longer AI ran vs. you |

An autonomy ratio of `2.0x` means your AI worked twice as long as you did.

## How it works

Claude Code saves session transcripts in `~/.claude/projects/`. Subagent sessions are stored in `<uuid>/subagents/` subdirectories. This tool scans both and separates them.

**Zero dependencies. No data sent anywhere. Runs entirely local.**

## Related tools

| Tool | What it checks |
|------|----------------|
| **cc-agent-load** | How much is YOU vs. AI? |
| [cc-session-stats](https://github.com/yurukusa/cc-session-stats) | Total usage stats |
| [cc-personality](https://github.com/yurukusa/cc-personality) | What kind of developer are you? |
| [cc-wrapped](https://yurukusa.github.io/cc-wrapped/) | Your AI year in review |

## License

MIT
