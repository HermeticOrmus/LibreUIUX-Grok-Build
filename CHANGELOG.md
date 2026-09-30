# Changelog

## [1.0.0] - 2026-09-30

The Grok edition: the melted skills install as a Grok plugin, and the same marketplace installs every LibreUIUX-Claude-Code plugin, pinned to one commit of the pack. The [kintsugi ledger](./LEDGER.md) records each v0 crack and its seal.

### Added

- `plugins/libreuiux-grok/`, the Grok-native plugin (`.grok-plugin/plugin.json`, version 1.0.0) with the two melted skills: `design-principles`, `ui-critique`.
- `.grok-plugin/marketplace.json` (`libreuiux-grok`): the Grok-native plugin plus all 71 LibreUIUX-Claude-Code plugins as remote entries pinned to pack commit `cf9113c37cf7d3b8019c775377c1b9fb1827e744`.
- `scripts/pin-pack.sh`: re-pins the pack entries to the pack's `main`, adds new pack plugins, drops removed ones, and prints the diff; `--check` fails on an unreachable SHA or a changed plugin list.
- `.github/workflows/validate.yml`: `grok plugin validate`, the dogfood copy check, the doc install-line check, the pin check, and an install of every entry into a clean `GROK_HOME`.
- Issue forms for feedback, routing misses and plugin proposals, with the `feedback`, `routing-miss` and `plugin-proposal` labels.
- [LEDGER.md](./LEDGER.md), [stubs/README.md](./stubs/README.md), "Ways to contribute" in [CONTRIBUTING.md](./CONTRIBUTING.md), and an Acknowledgments section crediting wshobson/agents for 66 of the pack plugins.

### Changed

- Install is `grok plugin marketplace add HermeticOrmus/LibreUIUX-Grok-Build` then `grok plugin install libreuiux-grok@libreuiux-grok --trust`. The folder copy still works from the new path, `plugins/libreuiux-grok/skills/*`.
- Melted skills moved from `skills/` to `plugins/libreuiux-grok/skills/`; the seven stubs moved to `stubs/`. The `.grok/skills/` dogfood copy stays and matches both.
- The v0 bundle stub `.grok/plugins/libreuiux-core/` moved to `stubs/libreuiux-core/`, marked superseded.
- README gains the family header, the marketplace install and the real Depth table; QUICK_START, AGENTS.md, DEPTH_MATRIX and MELT_RULES follow the new paths. `templates/AGENTS.modern-webapp.md` is unchanged.

### Fixed

- Stubs no longer install as if they were playbooks: their descriptions start "Stub, not a playbook." and name the pack plugin that holds the real depth, or say that none does.
- The v0 plugin folder installed as an unversioned plugin with no skills; the new plugin validates with its two skills.

### Upgrading from v0

- If you copied `skills/*` into a project or `~/.grok/skills/`, remove the seven stub folders from that copy, or switch to the marketplace install so `grok plugin update` brings changes.
- Paths that pointed at `skills/<name>` now point at `plugins/libreuiux-grok/skills/<name>` (melted) or `stubs/<name>` (stubs).

## [0.1.0] — 2026-09-20

### Changed

- Melted `skills/design-principles/SKILL.md` and `skills/ui-critique/SKILL.md` into usable Grok skills (steps, checks, examples, output shape). Dogfood copies under `.grok/skills/` match.
- Rewrote [QUICK_START.md](./QUICK_START.md) for a clean-machine install (<5 min) with paths that exist in this repo.
- Updated [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md): 2 melted, 7 stub skills, 1 stub agent. No Claude inventory counts.
- Suite footers on README, QUICK_START, and AGENTS.md now link Reality OS plus the sibling Libre*-Grok-Build packs.

## [0.0.1] — 2026-09-19

### Added

- Public v0 scaffold for LibreUIUX-Grok-Build.
- Stub SKILL.md for first 9 skills + synthesis-orchestrator agent.
- README, LICENSE (MIT), GOLD_HAT, QUICK_START, CONTRIBUTING, SECURITY.
- Depth matrix + melt rules docs.
