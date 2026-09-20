# Depth matrix

Update this table when melting. Status words mean what they say:

| Status | Meaning |
|--------|---------|
| stub | Thin cue only. Usable as a reminder, not a playbook. |
| melted | Real Grok skill: when-to-use, steps, measurable checks, example, output shape. |

Never copy Claude plugin / agent / command totals into this inventory. Upstream [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code) is proof that the *job* exists, not a count this repo has earned.

| ID | Kind | Status | Source (Claude, for melt) | Notes |
|----|------|--------|---------------------------|-------|
| design-principles | skill | melted | plugins/design-mastery/skills/design-principles | Steps, pass/fail checks, button example. No fake scores. |
| design-vocabulary | skill | stub | beginner/design-vocabulary.md | Teach-cue only. |
| ui-critique | skill | melted | .claude/commands/ui-critique.md | Dimensions, severity, remediations. No `/10` card, no slash-command theater. |
| ui-review | skill | stub | .claude/commands/ui-review.md | Multi-surface review still thin. |
| ui-responsive | skill | stub | .claude/commands/ui-responsive.md | Breakpoint cue only. |
| accessibility-audit | skill | stub | plugins/accessibility-compliance | WCAG pointer only. |
| brand-systems | skill | stub | plugins/design-mastery/skills/brand-systems | Token cue only. |
| premium-saas-design | skill | stub | plugins/design-mastery/skills/premium-saas-design | Surface cue only. |
| frontend-perf | skill | stub | plugins/application-performance | CWV cue only. |
| synthesis-orchestrator | agent | stub | .claude/agents/synthesis-master.md | Coordinates the skills; not a melted specialist. |

This repo now: **2 melted skills**, **7 stub skills**, **1 stub agent**.

Dogfood copies of every skill live at `.grok/skills/<id>/SKILL.md` and must match `skills/<id>/SKILL.md`.

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Sibling Libre*-Grok-Build packs: [README suite footer](../README.md).
