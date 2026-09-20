---
name: ui-critique
description: Critique a UI for hierarchy, spacing, contrast, interaction, and clarity. Use when reviewing components or screens.
---

# UI Critique

Daily critique loop for a single component or one screen. Truth over flattery. Measurable findings beat adjectives.

Gold Hat: teach the *why* of each finding. A critique that only lists defects extracts attention; a critique that leaves a reusable rule empowers the next pass.

## When to use

- After a non-trivial visual change
- When asked to "look at this button / card / form / page"
- Before handing a surface to engineering, or before calling it done

Use `design-principles` first if the job or focal point is unnamed. Use `ui-review` (still a stub) for multi-screen flow, empty/error/loading completeness, and handoff notes. Use `accessibility-audit` and `ui-responsive` (stubs) for a dedicated WCAG or breakpoint pass — do not pretend those skills are melted, and do not skip the issues you can already see.

Do not invent a numeric quality score. Severity ranks are enough.

## Operating steps

1. **Restate the job** in one line (who, task, primary action). If unknown, ask or infer from copy and say you inferred it.
2. **Walk the dimensions** below. For each finding: location (file/line or element), current behavior, why it fails, exact remediation.
3. **Rank by severity.** Critical → high → medium → low. Cap the first patch list at what a person can do in one sitting.
4. **Name strengths** only when they are real (a clear primary action, a consistent scale). Do not pad.
5. **Hand off leftovers** to the matching stub skill (`accessibility-audit`, `ui-responsive`, `frontend-perf`) instead of writing a fake full audit.

## Dimensions

### Hierarchy and focal point

Is there one place the eye lands? Does the primary action outrank secondary and tertiary?

Look for: competing CTAs, title and badge at the same weight, decorative illustration louder than the task.

### Spacing rhythm

Is gap/padding on the project scale? Do related items sit closer than unrelated groups?

Look for: mixed `gap` steps in one cluster, 13/15/17px accidents, section breaks that equal row gaps.

### Contrast and readability

Body text ≥ 4.5:1 against its background (WCAG 2.2 AA). Large text and UI components ≥ 3:1. Placeholder and disabled text often fail — check them.

If you did not measure, mark the finding **unverified** and say how to measure. Do not invent a ratio.

### Type

Limited scale. Line length roughly 45–75 characters for reading blocks. Line-height that does not collide with the next row. Weight used for hierarchy, not decoration.

### Interaction and states

Default, hover, focus, active, disabled, loading, error — whichever the control can enter. Missing focus is a defect, not polish.

- Focus: visible ring or equivalent, not `outline: none` without a replacement.
- Tap/click target: prefer **44×44 CSS px** (platform convention). WCAG 2.2 AA SC 2.5.8 floor is **24×24**. Say which bar you are using.
- Motion: one purpose (feedback, orientation). Honor `prefers-reduced-motion`. Decoration that delays the task is noise.

### Copy clarity

Does the control say what it does? Is error text specific and next-step shaped? Icon-only controls need an accessible name (that is also an a11y finding — list it here and point at `accessibility-audit`).

### System fit

Colors, type, radius, elevation from the project's tokens — or flagged as one-offs. Do not demand a design system the repo does not have; demand internal consistency.

## Severity

| Rank | Meaning | Example |
|------|---------|---------|
| Critical | Blocks the job or fails AA contrast/focus/name on a primary control | Primary submit is an unfocusable `<div>`; body text unverified-but-obviously faint on a wash |
| High | Users will hesitate or miss the action | Two equal CTAs; 28px tap target on a mobile submit |
| Medium | System drift or rhythm debt | Off-scale 13px gap; hover present, focus missing |
| Low | Polish | Radius 2px off the scale; motion that is taste, not access |

If unsure between two ranks, pick the higher and say why.

## Worked example — weak submit

Job: save profile name. Primary action: Save.

```html
<div class="save" onclick="save()">Save</div>
<span style="color:#9ca3af;font-size:12px">Cancel</span>
```

Critique (abridged):

```markdown
## Job
Signed-in user saves a display name. Primary action: Save.

## Findings
1. **Critical — interaction.** `div` + `onclick` is not a button: no keyboard role, no default focus. Remediation: `<button type="submit">Save</button>`.
2. **High — hierarchy.** Cancel is a `<span>` with no action affordance; Save has no filled/weight advantage in CSS (not shown). Remediation: Save = primary button; Cancel = `type="button"` quiet action that actually cancels.
3. **High — contrast (unverified).** `#9ca3af` on a typical white page is often near the AA line — measure before claiming a ratio. If it fails, darken Cancel or do not use gray-as-the-only-quiet-signal.
4. **Medium — target.** Text-sized hit area. Remediation: min 44×44 CSS px (or 24×24 if you are explicitly targeting SC 2.5.8 only).

## Strengths
Copy is short and the verb is correct.

## Fixes now
1. Real submit button with visible focus ring.
2. Quiet Cancel button, same height, trailing aligned.
3. Measure contrast on both labels; fix tokens if below AA.

## Leftovers
Full name/role/keyboard pass → `accessibility-audit` (stub). Narrow viewports → `ui-responsive` (stub).
```

That is a critique: locations, severity, remediations, leftovers. Not a `/10` scorecard.

## Output shape

```markdown
## Job
[who / task / primary action]

## Strengths
- [only real ones]

## Findings (severity-ranked)
1. **[Critical|High|Medium|Low] — [dimension].** [where] [what] [why]
   Remediation: [exact change]
2. …

## Fixes now
1. …
2. …
3. …

## Leftovers
- [skill] — [what you did not pretend to finish]
```

## Quality bar

A pass is done when every finding is specific, ranked, and remediable, and the teach-while-fixing sentence is implicit in the *why*. Refuse vibe-only notes ("make it pop", "more modern") — translate them through `design-principles` or drop them.

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Gold Hat: [GOLD_HAT.md](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build/blob/main/GOLD_HAT.md). Sibling Libre*-Grok-Build packs: [README suite footer](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build/blob/main/README.md).
