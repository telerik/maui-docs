# Repository Documentation Accessibility Assessment

**Assessment date:** 2026-10-30.

**Status: Provisional source-pattern baseline.** All eligible articles were processed; the checks are deterministic Markdown-source indicators and do not replace expert semantic review. This assessment does not evaluate rendered behavior, site interaction, product functionality, UI components, code correctness, image pixels, or WCAG conformance.

## Average Scores

- **Articles scored:** 1,329
- **Articles excluded:** 31
- **Overall documentation accessibility score:** 4.5 / 5.0

| Dimension | Average score (1–5) |
|---|---:|
| Heading Structure | 4.5 |
| Alternative Text | 4.5 |
| Link Text Clarity | 4.9 |
| Plain Language | 3.1 |
| Table Accessibility | 4.9 |
| Formatting Independence | 5.0 |
| Callout Structure | 5.0 |
| Code Block Accessibility | 4.9 |

## Summary

The weighted repository mean is **4.5/5.0** across 1,329 scored articles. The strongest dimension(s) are **Formatting Independence, Callout Structure** (5.0/5.0); the weakest dimension(s) are **Plain Language** (3.1/5.0).
Critical findings occur in **1** articles; High findings occur in **43** articles; **43** articles contain at least one Critical or High finding.
The source scan found 1,133 Markdown/HTML image references; 0 lack alt text or use a generic alt label. It flagged 0 image occurrence(s) for human review because their purpose cannot be determined from Markdown source alone. Alt-text relevance cannot be verified without evaluating image pixels.

The most common recurring patterns detected are:
- **Medium — Long sentences (over 25 words):** 862 articles
- **Low — Long sentences (over 25 words):** 276 articles
- **Medium — Vague or empty heading labels:** 272 articles
- **Medium — Non-descriptive or bare URL links:** 47 articles
- **Medium — Code blocks lack introductory prose:** 40 articles
- **Medium — Same link text used for different destinations:** 30 articles
- **High — Data tables lack header rows:** 25 articles
- **Medium — Skipped heading levels:** 24 articles

### Scope and Limitations

This baseline inspects Markdown source only. It recognizes YAML frontmatter, fenced code blocks, Markdown/HTML tables, Markdown/HTML images and links, common callout syntax, and Jekyll include directives. Included snippet content is not expanded. Alt-text relevance, redundancy, and adequacy cannot be verified without image pixels; link destination behavior is not tested. Plain-language scoring uses sentence length as a proxy and does not assess jargon, voice, or vocabulary. Table scoring does not assess layout use or complex header relationships; callout scoring checks syntax consistency rather than context; code scoring checks language tags and nearby introductory prose, not placeholder clarity or command outcomes. Scores indicate detected source patterns, not WCAG conformance.

## Inclusion and Exclusion Counts

- **Markdown files inventoried:** 1,376.
- **In-scope source candidates:** 1,360 after excluding repository/support and audit-output directories.
- **Included and scored:** 1,329.
- **Eligible but not scored:** 0.
- **Source candidates excluded by publication/configuration/content scope:** 31.
- **Additional Markdown files excluded by location:** 16.
- **Total Markdown files outside the scored set:** 47.

| Exclusion reason | Files |
|---|---:|
| Directory excluded: `.git/` | 0 |
| Directory excluded: `.github/` | 15 |
| Directory excluded: `node_modules/` | 0 |
| Directory excluded: `_site/` | 0 |
| Directory excluded: `bin/` | 0 |
| Directory excluded: `obj/` | 0 |
| Directory excluded: `accessibility-audit/` | 1 |
| Excluded by site config: README.md/copyright.md | 2 |
| Reusable content templates/snippets (_contentTemplates/) | 17 |
| Generated API reference (_assetsApi/api/) | 1 |
| Unpublished by frontmatter (publish/published: false) | 11 |
| Excluded by _config.yml: controls/chart/how-to | 0 |

The exclusion counts above use one primary reason per file. The two site-excluded files with unpublished frontmatter (README.md and copyright.md) are counted under the site-config exclusion to avoid double counting. `controls/chart/how-to` is configured as excluded but contains no Markdown files. Knowledge-base articles remain in scope because `_config.yml` excludes them only from navigation, not publication. Files with either `publish: false` or `published: false` frontmatter are excluded. API reference output is excluded from scoring.

**Validation:** Every included article was scored; eligible count equals scored count. No article failed source parsing.

## Critical and High Issues

Critical findings are listed before High findings; findings within each severity are grouped by article. Lines refer to source Markdown. Repeated occurrences of the same pattern within an article are summarized in the issue description.

### Critical Findings

| Severity | Article | Line | Dimension | Issue | Recommended Fix |
|---|---|---:|---|---|---|
| Critical | `knowledge-base/nuget-error-maui-check-tool.md` | 45 | Link Text Clarity | All detected links use non-descriptive text. | Replace generic link labels with text that identifies each destination or action. |

### High Findings

| Severity | Article | Line | Dimension | Issue | Recommended Fix |
|---|---|---:|---|---|---|
| High | `controls/accordion/overview.md` | 25 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/aiprompt/localization.md` | 18 | Table Accessibility | 1 empty data cell(s) were detected. | Provide a value such as “Not applicable” where an empty cell is not meaningful. |
| High | `controls/autocomplete/data-binding.md` | 38 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/autocomplete/events.md` | 30 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/autocomplete/methods.md` | 45 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/autocomplete/overview.md` | 34 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/autocomplete/suggest-mode.md` | 58 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/chart/behaviors/pan-and-zoom-behavior.md` | 118 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/chart/behaviors/selection-behavior.md` | 184 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/chart/behaviors/tooltip-behavior.md` | 106 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/chart/behaviors/trackball-behavior.md` | 103 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/collectionview/data-binding.md` | 49 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/navigationview/overview.md` | 31 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/richtexteditor/toolbar/overview.md` | 38 | Table Accessibility | 1 empty data cell(s) were detected. | Provide a value such as “Not applicable” where an empty cell is not meaningful. |
| High | `controls/richtexteditor/working-with-images/insert-images.md` | 40 | Table Accessibility | 2 empty data cell(s) were detected. | Provide a value such as “Not applicable” where an empty cell is not meaningful. |
| High | `controls/scheduler/specialslots/overview.md` | 40 | Heading Structure | The article contains 2 H1 headings. | Keep one page title and use H2-H6 for article sections. |
| High | `controls/speechtotextbutton/winui-support.md` | 26 | Table Accessibility | 1 empty data cell(s) were detected. | Provide a value such as “Not applicable” where an empty cell is not meaningful. |
| High | `installation/licensing/license-errors-warnings.md` | 30 | Table Accessibility | 4 empty data cell(s) were detected. | Provide a value such as “Not applicable” where an empty cell is not meaningful. |
| High | `knowledge-base/add-clear-button-tabview-header-net-maui.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/autocomplete-cursor-customization.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/button-howto-create-circle-button.md` | 13 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/change-telerik-theme-runtime.md` | 13 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/chart-dash-series.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/chart-palette-mvvm.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/collectionview-scrollbar-visible-android.md` | 13 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/combobox-calculate-dropdown-width.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/correcting-upside-down-image-imageeditor-dotnet-maui.md` | 15 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/custom-appointment-scheduler-net-maui.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/custom-localization-dotnet-maui-dataform.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/data-binding-qrcode-net-maui.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/datagrid-apply-hover-style-decorationstyle-cellcontenttemplate.md` | 117 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/entry-cursor-customization.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/entry-visual-states.md` | 13 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/extend-busyindicator-coverage-flyout-net-maui.md` | 23 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/extracting-point-data-from-signature-signaturepad-dotnet-maui.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/ios-maui-provisioning-profile-not-found.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/listview-cross-orientation-nesting.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/load-tab-content-on-demand-net-maui.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/maui-managed-vtable-types-notsupportedexception.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/nuget-error-maui-check-tool.md` | 15 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/nuget-package-restore-fails.md` | 13 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/remaining-tasks-radial-gauge-dotnet-maui.md` | 13 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |
| High | `knowledge-base/telerik-schema-error-cannot-resolve-type.md` | 14 | Table Accessibility | 1 data table(s) lack a detectable header row. | Mark the first row as table headers (Markdown header separator or HTML <th> cells). |


## Scoring and Validation Method

Each dimension is scored from 1 (Poor) to 5 (Excellent); an absent content type receives 5. Article scores use the weighted average: Heading Structure 20%, Alternative Text 20%, Link Text Clarity 15%, Plain Language 15%, Table Accessibility 10%, Formatting Independence 10%, Callout Structure 5%, and Code Block Accessibility 5%. The repository score is the mean of per-article weighted scores. Displayed averages are rounded to one decimal place.

Validation totals: 1,360 source candidates = 1,329 scored + 31 publication/configuration/content exclusions + 0 eligible but unscored. The full Markdown inventory is 1,376, including 16 files excluded by directory. The JSONL contains 1,329 records, one per scored article.

## Machine-Readable Scores

See [`scores.jsonl`](scores.jsonl) for one JSON record per scored article, including dimension scores, weighted score, Critical/High findings, recurring patterns, and image cases requiring human review.
