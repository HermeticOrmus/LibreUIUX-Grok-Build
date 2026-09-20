---
name: design-principles
description: Timeless UI design principles for Grok Build. Use when designing or reviewing visual hierarchy, spacing, typography, color, and composition.
---

# Design Principles

Apply measurable, timeless principles. These are observations about how people see — not taste, not trend, not a score.

Gold Hat: name the user job first, then teach the principle while you fix the surface. Leave the person more able to judge the next screen without you.

## When to use

- Designing a new component or screen
- Something "feels off" and you need a named cause
- Translating a vague request ("make it nicer") into a principle + a change
- Reviewing hierarchy, spacing, type, color, or composition before a critique pass

Do not use this skill as a full ship audit. After the visual system is named, hand to `ui-critique` (structure + interaction; melted in this pack) and `accessibility-audit` (WCAG; still a stub). Call the stub; do not invent its depth.

## Operating steps

1. **Name the job.** Who is this for, what must they accomplish, what is the one primary action?
2. **Find the focal point.** Blur the layout in your head (or drop opacity). One element should still read as first. If two compete, hierarchy failed.
3. **Walk the principles below** against that job. Record only findings you can point at (element + current value + principle).
4. **Propose three concrete fixes** (or fewer if the surface is already clean). Each fix names the principle it serves.
5. **Teach one sentence.** Why this change, in language the next designer can reuse.

Stop if you cannot name the user job. Ask. Guessing a focal point is extraction.

## Principles (measurable)

### Hierarchy

Not every element is first. Scale, weight, color, position, space, and elevation decide the order the eye follows.

| Check | Pass | Fail |
|-------|------|------|
| Focal point | One dominant action or title after a 50% blur | Two CTAs or a title and a badge of equal weight |
| Type steps | Distinct heading / body / meta sizes | Heading and body within ~2px of each other |
| Action color | Primary action is the most saturated / contrasting control | Ghost, link, and primary all equally loud |

### Proximity and grouping

Items near each other read as related. Equal gaps between every row destroy groups.

| Check | Pass | Fail |
|-------|------|------|
| In-group gap | Tight, repeated (e.g. 8px label→field) | Label closer to the next field than to its own |
| Between-group gap | Clearly larger than in-group (often 2–4×) | One leftover 13px gap that matches nothing |
| Similarity | Same kind of card / chip / row shares radius, padding, shadow | Each card invents its own chrome |

### Alignment

Shared edges beat optical "almost."

| Check | Pass | Fail |
|-------|------|------|
| Shared edge | Titles, fields, and actions share one vertical line | Logo, nav, and headline each inset differently |
| Grid | Columns start and end on the same tracks | A card hangs 6px off the content column |

### Repetition

Repeated decisions become a system. One-off values are bugs until proven otherwise.

Keep consistent: radius, elevation steps, spacing units (4 or 8), "primary means action," heading styles.

Flag any spacing that is not on the project's scale (13px, 15px, 17px are the usual accidents).

### Contrast

Difference creates both interest and access.

- Body text vs background: **4.5:1** (WCAG 2.2 AA)
- Large text (18px regular or 14px bold) and UI chrome vs adjacent color: **3:1**
- Color is never the only status signal (pair with text or icon)

Do not invent a contrast ratio. If you did not measure (DevTools, a contrast checker, or known token pair), say **unverified**.

### Whitespace

Empty space groups, emphasizes, and calms. Cramming "to fit more" is usually a hierarchy failure, not a space shortage.

| Check | Pass | Fail |
|-------|------|------|
| Isolation | Primary action has more padding than sibling text | CTA flush against a divider and a footnote |
| Section rhythm | Related blocks share one inset; sections step up | Every block uses the same 16px pad, so nothing is a section |

### Balance and unity

The surface should feel like one system. Move any one control to another page — if it looks foreign, unity failed (tokens, type, radius, or voice drifted).

## Problem → principle → fix

| Complaint | Principle | First fix |
|-----------|-----------|-----------|
| "I don't know where to look" | Hierarchy | One focal point: enlarge the title or quiet the competing chrome |
| "It feels cluttered" | Whitespace / proximity | Increase between-group gap; keep in-group tight |
| "It feels random" | Alignment / repetition | Snap to one edge and one spacing scale |
| "It feels cheap / loud" | Contrast / whitespace | Reduce competing saturation; give the primary action room |
| "These fields look unrelated" | Proximity / similarity | Cluster label+control; match padding on siblings |

## Worked example — primary button

Job: submit a short form. Primary action: Save.

Weak:

```html
<button>Save</button>
<a href="#">Cancel</a>
```

Default browser chrome, link and button compete, no focus treatment, tap target is content-sized.

Stronger (principle-tagged, framework-agnostic):

```html
<button type="submit" class="btn-primary">Save</button>
<button type="button" class="btn-quiet">Cancel</button>
```

- **Hierarchy:** Save is filled; Cancel is quiet text/ghost. One dominant action.
- **Repetition:** Both use the same height, radius, and type size from the project scale.
- **Contrast:** Label vs fill meets 4.5:1 (measure the actual tokens; do not claim a ratio you did not check).
- **Whitespace:** Horizontal padding ≥ 16px; height ≥ 44px so the target is the control, not the word.
- **Alignment:** Buttons share a baseline / trailing edge with the fields above.

Three concrete fixes if you only have the weak markup: (1) make Save the only filled control, (2) put both on the spacing scale with a 44px min height, (3) add a visible focus ring (3:1 against adjacent background) — then run `ui-critique` for states and `accessibility-audit` for names/roles.

## Output shape

```markdown
## Job
[who / task / primary action]

## Focal point
[what should win] — [does it?]

## Findings
- [principle] — [element] — [current] → [needed]

## Fixes (≤3)
1. [change] — serves [principle]
2. …
3. …

## Teach
[one reusable sentence]
```

If nothing is wrong, say so. Empty findings are allowed. Invented issues are not.

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Gold Hat: [GOLD_HAT.md](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build/blob/main/GOLD_HAT.md). Sibling Libre*-Grok-Build packs: [README suite footer](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build/blob/main/README.md).
