# LOCALIFE Agent Register

Maintained by the Master Supervisor (main Claude Code session). Definitions live in `.claude/agents/`.

| # | Agent ID | Role | Model | Tools | Edit scope | Phases |
|---|---|---|---|---|---|---|
| 0 | `localife-supervisor` | Master Supervisor / CTO / QC (main session, not a subagent) | session | all | project records, approvals | all |
| 1 | `localife-design-guardian` | Design System Manager | opus | Read, Write, Edit, Glob, Grep, Bash | tokens, `docs/design-system/` | 0, 1, 4, 7 |
| 2 | `localife-creative-director` | Creative Director / UX-UI | opus | Read, Write, Glob, Grep | plan docs only (no code) | 1, 2, 3, 5 |
| 3 | `localife-frontend-architect` | Next.js Architect | opus | Read, Write, Edit, Glob, Grep, Bash | app foundation, shared components, data | 0, 1, 3, 6, 8 |
| 4 | `localife-page-builder` | Page Developer | sonnet | Read, Write, Edit, Glob, Grep, Bash | assigned page routes only | 3, 4, 5 |
| 5 | `localife-visual-assets` | Image Director / Asset Manager | sonnet | Read, Write, Edit, Glob, Grep, Bash, WebSearch, WebFetch | `public/images/`, image manifest | 2, 4 |
| 6 | `localife-content-strategist` | Content / Storytelling | sonnet | Read, Write, Edit, Glob, Grep, WebSearch, WebFetch | `src/content/` | 2, 4, 5 |
| 7 | `localife-conversion` | Conversion Specialist | sonnet | Read, Write, Edit, Glob, Grep, Bash | forms, CTA wiring | 5, 6 |
| 8 | `localife-seo` | SEO Specialist | sonnet | Read, Write, Edit, Glob, Grep, Bash, WebSearch, WebFetch | metadata, sitemap, robots | 6, 8 |
| 9 | `localife-qa` | QA and Accessibility | opus | Read, Write, Glob, Grep, Bash | `tests/`, `docs/qa/` only | 7, 8 |
| 10 | `localife-performance` | Performance Engineer | sonnet | Read, Write, Edit, Glob, Grep, Bash | perf config, image/font delivery | 7, 8 |

## Rules
- Subagents are the default mechanism. Experimental agent teams stay off unless the owner approves.
- Every task uses the handoff format in `CLAUDE.md`; every agent returns the completion report with evidence.
- QA and Creative Director do not edit application code by design.
- Update this register whenever an agent is added, removed or its scope changes.
