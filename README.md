# LibreUIUX-Grok-Build

**UI/UX depth for [Grok Build](https://github.com/HermeticOrmus/grok-build-reality-os)** — ported and melted from [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code), not a dumb copy.

> Status: **local scaffold (v0)** — public GitHub repo not created yet.  
> Diego: say **create repo** to publish `HermeticOrmus/LibreUIUX-Grok-Build`.

## Why this exists

LibreUIUX owns Claude Code UI/UX depth (~70 plugins, design vocabulary, synthesis). Grok Build needs the same *job* with Grok-native skills, agents, `.grok/`, and truth-seeking voice.

## Install (&lt;5 min)

See [QUICK_START.md](./QUICK_START.md).

```bash
mkdir -p .grok/skills
cp -R skills/* .grok/skills/
```

Doctrine: install [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine first.

## Depth matrix (honest)

| Artifact | v0 scaffold | Upstream Claude (proof) |
|----------|-------------|-------------------------|
| Skills (melted bodies) | 9 stubs → fill next | ~74 SKILL.md |
| Agents | 1 (`synthesis-orchestrator`) | ~153 agent files |
| Plugins | 1 core bundle stub | ~70 plugin dirs |
| Commands | as skill triggers | ~81 command files |

Counts on the right are **upstream proof**, not this repo's claim until melted.

## First skills

| Skill | Job |
|-------|-----|
| design-principles | Core visual judgment |
| design-vocabulary | Shared UI language / teach cue |
| ui-critique | Daily critique loop |
| ui-review | Broader review |
| ui-responsive | Breakpoints & fluid layout |
| accessibility-audit | WCAG-oriented audit |
| brand-systems | Brand / token coherence |
| premium-saas-design | Product SaaS surfaces |
| frontend-perf | CWV / ship-ready perf |

Agent: `AGENTS/synthesis-orchestrator.md` — multi-pillar pass.

## Layout (Grok Build)

```
skills/                 # install into .grok/skills or ~/.grok/skills
AGENTS/                 # suite agents
.grok/plugins/          # optional plugin bundle
templates/              # AGENTS.modern-webapp.md
docs/                   # DEPTH_MATRIX, MELT_RULES
```

Claude's `.claude/` → Grok's skills + `AGENTS.md` + `.grok/`. See sibling port map in the footprint folder.

## Gold Hat

[GOLD_HAT.md](./GOLD_HAT.md) — empower or extract?

## Suite

- Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os)
- Skills packs: [grok-skills](https://github.com/HermeticOrmus/grok-skills) · [grok-build-skills](https://github.com/HermeticOrmus/grok-build-skills)
- Claude proof: [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code)
- https://ormus.solutions

## License

MIT — see [LICENSE](./LICENSE).
