# LibreUIUX-Grok-Build

**UI/UX depth for [Grok Build](https://github.com/HermeticOrmus/grok-build-reality-os)** — ported and melted from [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code), not a dumb copy.

> Status: **public v0** — two skills melted (`design-principles`, `ui-critique`); the rest are honest stubs. See [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md).

## Why this exists

LibreUIUX owns Claude Code UI/UX depth. Grok Build needs the same *job* with Grok-native skills, agents, `.grok/`, and truth-seeking voice. This repo counts only what it has melted.

## Install (<5 min)

See [QUICK_START.md](./QUICK_START.md) for clone, dogfood, project-local, and user-global paths.

```bash
git clone https://github.com/HermeticOrmus/LibreUIUX-Grok-Build.git
cd LibreUIUX-Grok-Build
# Dogfood: .grok/skills/ already has the skill bodies.
# Other project: cp -R skills/* /path/to/your-web-project/.grok/skills/
```

Doctrine: install [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine first. Merge [templates/AGENTS.modern-webapp.md](./templates/AGENTS.modern-webapp.md); do not replace doctrine.

## Depth (honest)

| Artifact | This repo now | Upstream Claude |
|----------|---------------|-----------------|
| Skills | 2 melted + 7 stubs | Proof the job exists; not our inventory |
| Agents | 1 stub (`synthesis-orchestrator`) | Proof the job exists; not our inventory |
| Plugins | 1 core bundle stub | Proof the job exists; not our inventory |

Do not paste Claude plugin/agent/command totals here. Update [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md) when something melts.

## Skills

| Skill | Status | Job |
|-------|--------|-----|
| design-principles | melted | Core visual judgment |
| ui-critique | melted | Daily critique loop |
| design-vocabulary | stub | Shared UI language / teach cue |
| ui-review | stub | Broader review |
| ui-responsive | stub | Breakpoints and fluid layout |
| accessibility-audit | stub | WCAG-oriented audit |
| brand-systems | stub | Brand / token coherence |
| premium-saas-design | stub | Product SaaS surfaces |
| frontend-perf | stub | CWV / ship-ready perf |

Agent: `AGENTS/synthesis-orchestrator.md` — stub coordinator for a multi-pillar pass.

## Layout (Grok Build)

```
skills/                 # canonical SKILL.md bodies
AGENTS/                 # suite agents
templates/              # AGENTS.modern-webapp.md
docs/                   # DEPTH_MATRIX, MELT_RULES
.grok/skills/           # dogfood copy of skills/ (keep in sync)
.grok/plugins/          # optional plugin bundle stub
```

Claude's `.claude/` maps to Grok skills + `AGENTS.md` + `.grok/`. Melt rules: [docs/MELT_RULES.md](./docs/MELT_RULES.md).

## Gold Hat

[GOLD_HAT.md](./GOLD_HAT.md) — empower or extract?

## Suite

- Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os)
- This pack: [LibreUIUX-Grok-Build](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build)
- Sibling Libre*-Grok-Build packs: [Arch](https://github.com/HermeticOrmus/LibreArch-Grok-Build) · [Copy](https://github.com/HermeticOrmus/LibreCopy-Grok-Build) · [DevOps](https://github.com/HermeticOrmus/LibreDevOps-Grok-Build) · [Embed](https://github.com/HermeticOrmus/LibreEmbed-Grok-Build) · [FinTech](https://github.com/HermeticOrmus/LibreFinTech-Grok-Build) · [GameDev](https://github.com/HermeticOrmus/LibreGameDev-Grok-Build) · [GEO](https://github.com/HermeticOrmus/LibreGEO-Grok-Build) · [MLOps](https://github.com/HermeticOrmus/LibreMLOps-Grok-Build) · [MobileDev](https://github.com/HermeticOrmus/LibreMobileDev-Grok-Build) · [SecOps](https://github.com/HermeticOrmus/LibreSecOps-Grok-Build) · [SessionFlow](https://github.com/HermeticOrmus/LibreSessionFlow-Grok-Build) · [WhatsApp](https://github.com/HermeticOrmus/LibreWhatsApp-Grok-Build)
- Skills collections: [grok-skills](https://github.com/HermeticOrmus/grok-skills) · [grok-build-skills](https://github.com/HermeticOrmus/grok-build-skills)
- Claude proof: [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code)
- https://ormus.solutions

## License

MIT — see [LICENSE](./LICENSE).
