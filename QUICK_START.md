# Quick Start — LibreUIUX for Grok Build

> From zero to one critiqued component in under 5 minutes.

## Prerequisites

- Grok Build installed and working
- A web UI project (any framework)

## Install skills (repo-local)

```bash
git clone https://github.com/HermeticOrmus/LibreUIUX-Grok-Build.git  # after publish
cd your-web-project
mkdir -p .grok/skills
cp -R /path/to/LibreUIUX-Grok-Build/skills/* .grok/skills/
```

Or user-global:

```bash
mkdir -p ~/.grok/skills
cp -R /path/to/LibreUIUX-Grok-Build/skills/* ~/.grok/skills/
```

Optional: copy `templates/AGENTS.modern-webapp.md` into your project as `AGENTS.md` (merge with Reality OS; do not replace doctrine).

## First-run teach cue

In Grok Build, ask:

1. **Build** — "Create a modern primary button with hover and focus states using our design principles skill."
2. **Critique** — "Run ui-critique on that button: hierarchy, spacing, contrast, tap target, focus ring."
3. **Harden** — "Run accessibility-audit on the same component for WCAG 2.2 AA."

You just used melted LibreUIUX depth on Grok — not a Claude paste.

## Smoke checklist

- [ ] Skills visible to Grok (repo `.grok/skills` or `~/.grok/skills`)
- [ ] One component generated
- [ ] One critique returned with measurable notes
