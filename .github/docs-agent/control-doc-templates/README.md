# Article templates

These templates are consumed by the [Control Doc Author](../control-doc-author.agent.md) agent.
They mirror the wiki templates at <https://github.com/telerik/maui-docs/wiki> and are tuned to
match the conventions enforced by [../control-doc-style.md](../control-doc-style.md).

| Template | Purpose | Wiki source |
|----------|---------|-------------|
| [overview.md](overview.md) | Top-level control article (`position: 0`) | Control Overview Template |
| [getting-started.md](getting-started.md) | First-run install + define control | Control Getting Started Template |
| [visual-structure.md](visual-structure.md) | Anatomy of the control | Control Visual Structure Template |
| [feature.md](feature.md) | Any feature article (configuration, data binding, selection, templates, …) | Control Feature Template |
| [styling.md](styling.md) | Styling API of the control | Control Feature Template (styling variant) |
| [commands.md](commands.md) | `ICommand` members exposed by the control | Control Feature Template (commands variant) |
| [events.md](events.md) | Events raised by the control | Control Feature Template (events variant) |
| [methods.md](methods.md) | Public methods exposed by the control | Control Feature Template (methods variant) |

## Placeholders

Every template uses double-brace placeholders that the agent must fully substitute before writing the file:

| Placeholder | Example | Notes |
|-------------|---------|-------|
| `{{ControlName}}` | `NumericInput` | Display name used in headings and prose |
| `{{RadClassName}}` | `RadNumericInput` | The actual XAML/C# type |
| `{{control-slug}}` | `numericinput` | Lower-case, no separators, used in slugs and snippet ids |
| `{{product-url-segment}}` | `numericinput` | Path segment under `telerik.com/maui-ui/` |
| `{{Feature Title}}` / `{{feature-slug}}` | `Increment Step` / `increment-step` | Per-feature variants |
| `{{position}}` | `3` | Integer; do not collide with siblings |

Placeholders inside descriptive text (for example `{{describe the visible elements}}` in image alt text or `{{Task-oriented heading}}`) are instructions. Replace them with real content; never leave them in the article. Remove optional sections such as `## Known Limitations` when there is no content for them.

Generated articles must pass the quality gate described in [../control-doc-style.md](../control-doc-style.md#quality-gate-scoring-skills), which scores every article with the skills under `.github/skills/`.

## SDK samples are mandatory

For every getting-started, feature, styling, commands, events, and methods article there must be a matching sample in the SDKBrowser Demo Application.
The agent must verify this with the user before generating the article.
The cross-reference blockquote at the end of each article links to `{% slug sdkbrowser-app %}`.
