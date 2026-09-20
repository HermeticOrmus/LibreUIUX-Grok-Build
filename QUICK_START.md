# Quick Start — LibreUIUX for Grok Build

> From a clean machine to one critiqued component in under 5 minutes.

Doctrine first: put [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine (global Grok doctrine). This pack does not replace it.

## Prerequisites

- `git`
- Grok Build installed and able to see skills under `.grok/skills/` or `~/.grok/skills/`
- A web UI project you own, **or** this repo as the working tree

## Layout this file assumes

Verified against this repository (do not invent extra folders):

```
skills/<name>/SKILL.md          # canonical skill bodies (copy these)
AGENTS/synthesis-orchestrator.md
templates/AGENTS.modern-webapp.md
docs/DEPTH_MATRIX.md
docs/MELT_RULES.md
.grok/skills/<name>/SKILL.md    # dogfood copy; must match skills/
.grok/plugins/libreuiux-core/   # plugin stub; not required for first run
```

Melted (usable now): `skills/design-principles/SKILL.md`, `skills/ui-critique/SKILL.md`.  
Still stubs: the other seven skills + the orchestrator. Honest table: [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md).

## Install (pick one)

### A. Dogfood this repo (fastest)

```bash
git clone https://github.com/HermeticOrmus/LibreUIUX-Grok-Build.git
cd LibreUIUX-Grok-Build
# Skills are already at .grok/skills/ — open this folder in Grok Build.
```

### B. Install into your web project

```bash
git clone https://github.com/HermeticOrmus/LibreUIUX-Grok-Build.git ~/LibreUIUX-Grok-Build
cd /path/to/your-web-project
mkdir -p .grok/skills
cp -R ~/LibreUIUX-Grok-Build/skills/* .grok/skills/
```

Confirm the copy landed:

```bash
test -f .grok/skills/design-principles/SKILL.md
test -f .grok/skills/ui-critique/SKILL.md
ls .grok/skills
```

You should see nine skill directories, matching `skills/` in this repo.

### C. User-global

```bash
git clone https://github.com/HermeticOrmus/LibreUIUX-Grok-Build.git ~/LibreUIUX-Grok-Build
mkdir -p ~/.grok/skills
cp -R ~/LibreUIUX-Grok-Build/skills/* ~/.grok/skills/
```

Same two `test -f` checks as B, under `~/.grok/skills/`.

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

- [ ] `design-principles` and `ui-critique` files exist at the install path you chose
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
