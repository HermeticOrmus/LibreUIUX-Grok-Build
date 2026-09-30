# libreuiux-grok

The Grok-native LibreUIUX plugin. It carries the skills melted for Grok Build, and only those:

| Skill | Job | Melted from (pack) |
|-------|-----|--------------------|
| `design-principles` | Core visual judgment: hierarchy, proximity, alignment, contrast, whitespace | `design-mastery` plugin, `skills/design-principles` |
| `ui-critique` | Daily critique loop: severity-ranked findings with remediations, no `/10` card | the pack's `.claude/commands/ui-critique.md` |

Install:

```bash
grok plugin marketplace add HermeticOrmus/LibreUIUX-Grok-Build
grok plugin install libreuiux-grok@libreuiux-grok --trust
```

The seven stub skills are not in this plugin. They live in [stubs/](../../stubs/), and each names the pack plugin that holds the real depth, or says plainly that no pack plugin does. The same marketplace installs the pack plugins.

The `design-mastery` pack plugin also ships a skill named `design-principles`. Both install side by side; see [LEDGER.md](../../LEDGER.md) (K-10) for what is and is not verified about routing between them.

Manifest: [.grok-plugin/plugin.json](./.grok-plugin/plugin.json). Honest inventory: [docs/DEPTH_MATRIX.md](../../docs/DEPTH_MATRIX.md). The v0 bundle stub this plugin replaces is kept at [stubs/libreuiux-core/](../../stubs/libreuiux-core/).
