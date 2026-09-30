# Quick Start — LibreUIUX for Grok Build

> From a clean machine to one critiqued component in under 5 minutes.

Doctrine first: put [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine (global Grok doctrine). This pack does not replace it.

## Prerequisites

- Grok Build (`grok --version` prints a version)
- `git` and `jq` for the clone paths and the install-everything loop
- A web UI project you own, **or** this repo as the working tree

## Layout this file assumes

Verified against this repository (do not invent extra folders):

```text
plugins/libreuiux-grok/                      # the Grok-native plugin
plugins/libreuiux-grok/skills/<name>/SKILL.md  # melted skill bodies (copy these for the manual path)
stubs/<name>/SKILL.md                        # stub cues; not installed
AGENTS/synthesis-orchestrator.md
templates/AGENTS.modern-webapp.md
docs/DEPTH_MATRIX.md
docs/MELT_RULES.md
.grok-plugin/marketplace.json                # the plugin + every pack plugin, pinned
.grok/skills/<name>/SKILL.md                 # dogfood copy of the plugin skills and stubs
stubs/libreuiux-core/                        # v0 plugin bundle stub, kept as the record
```

Melted (usable now): `design-principles`, `ui-critique`, in `plugins/libreuiux-grok/skills/`.  
Still stubs: the other seven skills + the orchestrator. Honest table: [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md).

## Install (pick one)

### A. Marketplace (recommended)

```bash
grok plugin marketplace add HermeticOrmus/LibreUIUX-Grok-Build
grok plugin install libreuiux-grok@libreuiux-grok --trust
grok plugin details libreuiux-grok
```

Grok installs a plugin only with `--trust`, because a plugin can run hooks, MCP servers and skills on your machine. Without it, `grok plugin install` stops and asks you to re-run with the flag.

The same marketplace lists every [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code) plugin, pinned to one commit of the pack. Install the ones your project needs by name:

```bash
grok plugin install design-mastery@libreuiux-grok --trust
grok plugin install accessibility-compliance@libreuiux-grok --trust
```

Or install every entry (71 pack plugins plus the Grok-native one):

```bash
for p in $(grok plugin list --json --available | jq -r '.[] | select(.marketplace == "libreuiux-grok" and .status == "available") | .name'); do
  grok plugin install "$p@libreuiux-grok" --trust
done
```

`libreuiux-hooks` is format-compatible with Grok, but its behavior inside a Grok session is not verified yet (see [LEDGER.md](./LEDGER.md)). Skip it if you only want skills, agents and commands.

To pick up a new pin later: `grok plugin marketplace update`, then `grok plugin update`.

### B. Dogfood this repo

```bash
git clone https://github.com/HermeticOrmus/LibreUIUX-Grok-Build.git
cd LibreUIUX-Grok-Build
# A copy of the skills and stubs is already at .grok/skills/. Open this folder in Grok Build.
```

### C. Copy into your web project

The v0 path, for a project that should carry the skill files itself.

```bash
git clone https://github.com/HermeticOrmus/LibreUIUX-Grok-Build.git ~/LibreUIUX-Grok-Build
cd /path/to/your-web-project
mkdir -p .grok/skills
cp -R ~/LibreUIUX-Grok-Build/plugins/libreuiux-grok/skills/* .grok/skills/
```

Confirm the copy landed:

```bash
test -f .grok/skills/design-principles/SKILL.md
test -f .grok/skills/ui-critique/SKILL.md
ls .grok/skills
```

You should see two skill directories, matching `plugins/libreuiux-grok/skills/` in this repo. The stubs are not copied: they are pointers to pack plugins, not skills.

### D. User-global copy

```bash
git clone https://github.com/HermeticOrmus/LibreUIUX-Grok-Build.git ~/LibreUIUX-Grok-Build
mkdir -p ~/.grok/skills
cp -R ~/LibreUIUX-Grok-Build/plugins/libreuiux-grok/skills/* ~/.grok/skills/
```

Same two `test -f` checks as C, under `~/.grok/skills/`.

### Upgrading from v0

If you copied `skills/*` into a project or `~/.grok/skills/`, that copy holds all nine folders, stubs included. Remove the seven stub folders (`design-vocabulary`, `ui-review`, `ui-responsive`, `accessibility-audit`, `brand-systems`, `premium-saas-design`, `frontend-perf`) from the copy, or replace the copy with path A so updates arrive through `grok plugin update`.

### Optional project rules (merge, do not replace)

```bash
# From your web project — merge into existing AGENTS.md / .grok/AGENTS.md.
# Do not overwrite Reality OS doctrine.
cat ~/LibreUIUX-Grok-Build/templates/AGENTS.modern-webapp.md
```

Copy `AGENTS/synthesis-orchestrator.md` only when you want a multi-pillar pass. It is still a stub coordinator.

## First-run teach cue

In Grok Build, on a real component you own:

1. **Build** — "Create a primary button with hover and focus using the design-principles skill. Name the user job first."
2. **Critique** — "Run ui-critique on that button: hierarchy, spacing, contrast (measure or mark unverified), tap target, focus ring."
3. **Harden (stub)** — "List leftover a11y items for accessibility-audit. Do not invent a full WCAG score."

You used melted LibreUIUX depth on Grok — not a Claude paste, not a fake agent count.

## Smoke checklist

- [ ] `grok plugin list` shows `libreuiux-grok` (path A), or the two skill files exist at the copy path you chose (C or D)
- [ ] Grok can see those two skills
- [ ] One component generated with a named job + focal point
- [ ] One critique returned with severity-ranked findings and remediations (no `/10` score)
- [ ] No secrets in prompts, examples, or output

## Suite

- Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os)
- This pack: [LibreUIUX-Grok-Build](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build)
- Sibling Libre*-Grok-Build packs: [Arch](https://github.com/HermeticOrmus/LibreArch-Grok-Build) · [Copy](https://github.com/HermeticOrmus/LibreCopy-Grok-Build) · [DevOps](https://github.com/HermeticOrmus/LibreDevOps-Grok-Build) · [Embed](https://github.com/HermeticOrmus/LibreEmbed-Grok-Build) · [FinTech](https://github.com/HermeticOrmus/LibreFinTech-Grok-Build) · [GameDev](https://github.com/HermeticOrmus/LibreGameDev-Grok-Build) · [GEO](https://github.com/HermeticOrmus/LibreGEO-Grok-Build) · [MLOps](https://github.com/HermeticOrmus/LibreMLOps-Grok-Build) · [MobileDev](https://github.com/HermeticOrmus/LibreMobileDev-Grok-Build) · [SecOps](https://github.com/HermeticOrmus/LibreSecOps-Grok-Build) · [SessionFlow](https://github.com/HermeticOrmus/LibreSessionFlow-Grok-Build) · [WhatsApp](https://github.com/HermeticOrmus/LibreWhatsApp-Grok-Build)
- Skills collections: [grok-skills](https://github.com/HermeticOrmus/grok-skills) · [grok-build-skills](https://github.com/HermeticOrmus/grok-build-skills)
- Claude proof (upstream, not this inventory): [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code)
- https://ormus.solutions
