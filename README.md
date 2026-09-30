<p align="center">
  <img src="https://ormus.solutions/mascot/pixellab_liquid_to_swan.gif" alt="LibreUIUX Grok Build" width="128" style="image-rendering: pixelated;" />
</p>

<h1 align="center">LibreUIUX Grok Build</h1>

<p align="center">
  <em>UI/UX depth for Grok Build: Grok-native skills plus every LibreUIUX pack plugin, from one marketplace</em>
</p>

<p align="center">
  <a href="https://github.com/HermeticOrmus/LibreUIUX-Grok-Build/stargazers"><img src="https://img.shields.io/github/stars/HermeticOrmus/LibreUIUX-Grok-Build?style=flat-square&color=aa8142" alt="Stars" /></a>
  <a href="https://github.com/HermeticOrmus/LibreUIUX-Grok-Build/blob/main/LICENSE"><img src="https://img.shields.io/github/license/HermeticOrmus/LibreUIUX-Grok-Build?style=flat-square&color=aa8142" alt="License" /></a>
  <a href="https://github.com/HermeticOrmus/LibreUIUX-Grok-Build/commits"><img src="https://img.shields.io/github/last-commit/HermeticOrmus/LibreUIUX-Grok-Build?style=flat-square&color=aa8142" alt="Last Commit" /></a>
  <img src="https://img.shields.io/badge/UI%2FUX-aa8142?style=flat-square&logo=figma&logoColor=white" alt="UI/UX" />
  <img src="https://img.shields.io/badge/Grok_Build-aa8142?style=flat-square&logo=x&logoColor=white" alt="Grok Build" />
</p>

---

**UI/UX depth for [Grok Build](https://github.com/HermeticOrmus/grok-build-reality-os)** — ported and melted from [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code), not a dumb copy.

> Status: **v1.0.0**. Two skills are melted into the Grok-native plugin `libreuiux-grok` (`design-principles`, `ui-critique`). The other seven are honest stubs in [stubs/](./stubs/), each pointing at the pack plugin that holds the real depth, or saying plainly that none does. See [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md) and the [kintsugi ledger](./LEDGER.md).

## Why this exists

LibreUIUX owns Claude Code UI/UX depth. Grok Build needs the same *job* with Grok-native skills, agents, `.grok/`, and truth-seeking voice. This repo counts only what it has melted.

## Install

One marketplace brings both layers: the Grok-native plugin melted here, and every plugin of the [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code) pack, pinned to one commit of the pack. Grok reads the pack plugins as they are.

```bash
grok plugin marketplace add HermeticOrmus/LibreUIUX-Grok-Build
grok plugin install libreuiux-grok@libreuiux-grok --trust
```

Grok installs a plugin only with `--trust`, because a plugin can run hooks, MCP servers and skills on your machine. Read what you trust: each entry's source is linked in [.grok-plugin/marketplace.json](./.grok-plugin/marketplace.json).

Then add the pack plugins your project needs, for example:

```bash
grok plugin install design-mastery@libreuiux-grok --trust
grok plugin install accessibility-compliance@libreuiux-grok --trust
```

[QUICK_START.md](./QUICK_START.md) has the loop that installs every entry, the dogfood clone, and the manual copy path. From a clone:

```bash
git clone https://github.com/HermeticOrmus/LibreUIUX-Grok-Build.git
cd LibreUIUX-Grok-Build
# Dogfood: .grok/skills/ holds a copy of the skill bodies and stubs.
# Other project: cp -R plugins/libreuiux-grok/skills/* /path/to/your-web-project/.grok/skills/
```

Doctrine: install [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine first. Merge [templates/AGENTS.modern-webapp.md](./templates/AGENTS.modern-webapp.md); do not replace doctrine.

## Depth (honest)

| Artifact | This repo now | Where |
|----------|---------------|-------|
| Grok-native skills | 2 melted | `plugins/libreuiux-grok/skills/` |
| Stub skills | 7, not installed | `stubs/`, each names its pack plugin or says none |
| Agents | 1 stub (`synthesis-orchestrator`), not installed | `AGENTS/` |
| Plugins in the marketplace | 1 Grok-native + 71 pack entries | `.grok-plugin/marketplace.json`, pinned to one pack commit |

Pack entries are LibreUIUX-Claude-Code plugins installed through this marketplace. They are not melted here, and they are not counted as this repo's skills. Do not paste Claude plugin/agent/command totals here. Update [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md) when something melts, and run `scripts/pin-pack.sh` when the pack changes.

## Skills

| Skill | Status | Job | Pack |
|-------|--------|-----|------|
| design-principles | melted | Core visual judgment | melted from `design-mastery` |
| ui-critique | melted | Daily critique loop | melted from the pack's `/ui-critique` command |
| design-vocabulary | stub | Shared UI language / teach cue | no plugin one to one; nearest `design-mastery` |
| ui-review | stub | Broader review | no plugin one to one; nearest `design-mastery` |
| ui-responsive | stub | Breakpoints and fluid layout | no plugin yet |
| accessibility-audit | stub | WCAG-oriented audit | real depth in `accessibility-compliance` |
| brand-systems | stub | Brand / token coherence | real depth in `design-mastery` |
| premium-saas-design | stub | Product SaaS surfaces | real depth in `design-mastery` |
| frontend-perf | stub | CWV / ship-ready perf | real depth in `application-performance` |

Agent: `AGENTS/synthesis-orchestrator.md` — stub coordinator for a multi-pillar pass.

## Layout (Grok Build)

```text
plugins/libreuiux-grok/  # the Grok-native plugin: manifest + melted SKILL.md bodies
stubs/                   # stub skills + the v0 bundle stub; not installed
AGENTS/                  # suite agents
templates/               # AGENTS.modern-webapp.md
docs/                    # DEPTH_MATRIX, MELT_RULES
scripts/pin-pack.sh      # re-pins the pack entries to the pack's main
.grok-plugin/            # marketplace: the plugin + every pack plugin, pinned
.grok/skills/            # dogfood copy of the plugin skills and stubs (CI checks it)
```

Claude's `.claude/` maps to Grok skills + `AGENTS.md` + `.grok/`. Melt rules: [docs/MELT_RULES.md](./docs/MELT_RULES.md).

## Kintsugi ledger

Every crack found in v0 and how this release seals it, with the file that shows the seal: [LEDGER.md](./LEDGER.md).

## Feedback and contributing

Tell us what worked and what is missing with the [feedback form](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build/issues/new?template=feedback.yml). When Grok picks the wrong skill, file a [routing miss](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build/issues/new?template=routing-miss.yml). Ways to contribute are in [CONTRIBUTING.md](./CONTRIBUTING.md).

## Acknowledgments

66 of the 71 pack plugins this marketplace lists come from [wshobson/agents](https://github.com/wshobson/agents) by Seth Hobson and its contributors, used under the MIT License. The pack's [NOTICE.md](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/blob/main/NOTICE.md) lists each one with its author.

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
