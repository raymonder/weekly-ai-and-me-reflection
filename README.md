# weekly-ai-and-me-reflection

Version: 0.9

Codex skill for generating a weekly or on-demand AI collaboration reflection report from recent chat, agent, or coding-session transcripts, plus a static dashboard.

## What It Does

- Reviews recent AI collaboration transcripts.
- Summarizes what work was visible through AI interactions.
- Observes human collaboration style and prompt patterns.
- Produces evidence-based feedback for both the human and AI.
- Counts accepted deliverables, rework, and correction events heuristically.
- Compares with the previous weekly report.
- Updates a static `index.html` dashboard.
- Uses a machine-readable YAML block at the end of each report for trend aggregation.

## Install

```bash
cd ~/.codex/skills
git clone https://github.com/raymonder/weekly-ai-and-me-reflection.git
```

Restart Codex or open a new session so the skill metadata is loaded.

## Use

Ask for a weekly collaboration reflection:

```text
Generate this week's AI collaboration reflection report.
```

```text
Review my last 7 days of AI sessions and update the AI-and-me dashboard.
```

```text
用最近一周的对话生成一份 AI 协作周报，输出到 ./ai-and-me。
```

If transcript/session tools are unavailable, provide exported transcripts or a directory path.

## Outputs

Default output directory is `./ai-and-me` unless the user chooses another path:

```text
ai-and-me/
├── decisions.md
├── index.html
└── weekly/
    └── YYYY-MM-DD-report.md
```

`decisions.md` is optional. Use it for stable preferences or "do not re-raise this" decisions.

## Limits

- It can only analyze transcripts it can access.
- Counts are heuristic, not analytics-grade metrics.
- It should not invent criticism or praise when the transcript evidence is missing.
- It should not expose private transcript details, names, emails, account IDs, tenant names, or local paths unless explicitly requested for the generated report.
- It does not create automations by itself. Use the host app's automation/reminder feature if you want it to run weekly.

## Good Inputs

- Output directory.
- Date window.
- Transcript source or exported transcript files.
- Preferred human/AI display labels.
- Existing `decisions.md`, if any.
