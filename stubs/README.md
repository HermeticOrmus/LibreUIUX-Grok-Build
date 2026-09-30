# Stubs

A stub is a thin cue: a name, a one-line job, and a sentence or two of what to check. It is a reminder, not a playbook, so nothing here installs. Each stub names the pack plugin that holds the real depth, and that plugin installs from this repo's marketplace. Where no pack plugin holds the job one to one, the stub says so and points at the nearest depth.

| Stub | Job | Real depth (pack) | Install |
|------|-----|-------------------|---------|
| [design-vocabulary](./design-vocabulary/SKILL.md) | Shared UI language / teach cue | No plugin one to one: the pack's learning path [`beginner/design-vocabulary.md`](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/blob/main/beginner/design-vocabulary.md); nearest plugin [`design-mastery`](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/tree/main/plugins/design-mastery) | `grok plugin install design-mastery@libreuiux-grok --trust` |
| [ui-review](./ui-review/SKILL.md) | Broader review | No plugin one to one: the pack's [`.claude/commands/ui-review.md`](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/blob/main/.claude/commands/ui-review.md) sits outside any plugin; nearest plugin [`design-mastery`](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/tree/main/plugins/design-mastery) (`design-audit`) | `grok plugin install design-mastery@libreuiux-grok --trust` |
| [ui-responsive](./ui-responsive/SKILL.md) | Breakpoints and fluid layout | No plugin: the pack's [`.claude/commands/ui-responsive.md`](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/blob/main/.claude/commands/ui-responsive.md) sits outside any plugin | none yet |
| [accessibility-audit](./accessibility-audit/SKILL.md) | WCAG-oriented audit | [`accessibility-compliance`](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/tree/main/plugins/accessibility-compliance) | `grok plugin install accessibility-compliance@libreuiux-grok --trust` |
| [brand-systems](./brand-systems/SKILL.md) | Brand / token coherence | [`design-mastery`](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/tree/main/plugins/design-mastery) (`skills/brand-systems`) | `grok plugin install design-mastery@libreuiux-grok --trust` |
| [premium-saas-design](./premium-saas-design/SKILL.md) | Product SaaS surfaces | [`design-mastery`](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/tree/main/plugins/design-mastery) (`skills/premium-saas-design`) | `grok plugin install design-mastery@libreuiux-grok --trust` |
| [frontend-perf](./frontend-perf/SKILL.md) | CWV / ship-ready perf | [`application-performance`](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/tree/main/plugins/application-performance) | `grok plugin install application-performance@libreuiux-grok --trust` |

Also here: [libreuiux-core/](./libreuiux-core/), the v0 plugin bundle stub. It had no manifest and installed only a copy of the stub orchestrator. It is kept as the record; [plugins/libreuiux-grok](../plugins/libreuiux-grok/) replaces it.

The suite agent [AGENTS/synthesis-orchestrator.md](../AGENTS/synthesis-orchestrator.md) is also a stub coordinator. It stays where [AGENTS.md](../AGENTS.md) points, and nothing installs it: you merge it by hand. Its source in the pack, [`.claude/agents/synthesis-master.md`](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code/blob/main/.claude/agents/synthesis-master.md), also sits outside any plugin, so no pack plugin installs it either.

## Melt a stub

1. Write the skill to the melted bar in [docs/MELT_RULES.md](../docs/MELT_RULES.md) and [docs/DEPTH_MATRIX.md](../docs/DEPTH_MATRIX.md): when to use, steps, measurable checks, a worked example, an output shape.
2. `git mv stubs/<name> plugins/libreuiux-grok/skills/<name>`, drop the stub line, and give the frontmatter a routing description (`Use when ...`).
3. Copy it to `.grok/skills/<name>/SKILL.md` (CI checks the copy matches).
4. Update [docs/DEPTH_MATRIX.md](../docs/DEPTH_MATRIX.md), this table, and the README skills table.

The dogfood copies of these stubs in `.grok/skills/` match the files here, so a session opened in this repo sees them described as stubs.
