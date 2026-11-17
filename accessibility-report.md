---
publish: false
published: false
---

# Accessibility: Provisional Source-Screening Baseline

Audit date: **2026-11-17**  
Source Git HEAD: `001a93e0cb9fd0c0022dfcce50f2a7e1d9808f40`

This is a systematic automated screening of article source, not a comprehensive human accessibility review, a health percentage, or a WCAG conformance determination. Scores include absent-type defaults and unverified semantic checks; a high aggregate must not be interpreted as confirmation that all content is accessible.

## Average Scores

**1,370 articles scored; 46 existing Markdown files excluded; 0 articles unscored.** Every included article has eight integer dimension scores in `scores.jsonl`, sorted by repository-relative path. No per-article scores are reproduced in this report.

| Dimension | Weight | Mean screening score |
| --- | ---: | ---: |
| Heading structure and navigation | 20% | 5.0 |
| Alternative text quality | 20% | 4.8 |
| Link text clarity | 15% | 5.0 |
| Plain language and readability | 15% | 4.4 |
| Table accessibility | 10% | 5.0 |
| Color and formatting independence | 10% | 4.2 |
| Callout and admonition structure | 5% | 5.0 |
| Code block accessibility | 5% | 5.0 |
| **Overall mean** | **100%** | **4.8** |

For article `a`, the exact weighted score is `W(a) = sum(weight_percent[d] × integer_score[a,d]) / 100`. The overall mean is `sum(W(a)) / 1370`, **not** the mean of the already rounded article scores, nor a calculation using rounded dimension means. The integer weighted numerator summed across articles is **655970**; divide by `100 × 1370` before rounding.

All displayed scores use one decimal place with decimal **round-half-up** (`ROUND_HALF_UP`), with no intermediate rounding. JSONL preserves the exact weighted article value in `overall_score_unrounded` as well as the one-decimal `overall_score`; calculate with decimal arithmetic or integer weighted numerators rather than binary floating-point rounding.

## Summary

- **Strongest source-screening dimension:** heading structure, with no scored source signals. Table structure also rounds to 5.0 but includes one unparsed-table review candidate; neither result verifies expanded outlines, layout intent, or all header relationships.
- **Weakest dimensions:** formatting independence, followed by plain language. The leading actionable patterns are visually numbered paragraphs instead of native lists, and long prose sentences.
- **Confirmed Critical findings: 0; confirmed High findings: 0.** Unique articles with Critical: **0**; with High: **0**; with either: **0**; with both: **0**.
- **2,751 Medium/Low source signals across 830 articles:** 30 Medium signals across 28 articles, and 2,721 Low signals across 828 articles. These are editorial/structural signals, not demonstrated essential-access blockers.
- **Human Review Required: 1,054 cases across 785 articles.** Cases have `severity: null`, source lines, evidence, and a suggested review action in JSONL; they are not silently treated as verified passes.
- All 1,370 articles were decoded and parsed; `failed_checks` is empty for every record. The **baseline remains provisional** because semantic and rendered checks remain outstanding, not because any article was omitted after a parsing failure.

### Recurring Medium and Low patterns

Counts below are recorded signal occurrences, not duplicated entries from the per-dimension `violations` arrays. An article can occur in more than one row; a source line can contain more than one sentence signal. Every occurrence has original line-number evidence and a recommended fix in `recurring_issue_patterns`.

| Severity | Pattern | Signals | Unique articles | Original-source example |
| --- | --- | ---: | ---: | --- |
| Low | Visual step markers such as `**1.**`, not native Markdown list markers | 1,832 | 462 | `controls/accordion/getting-started.md:30` — `**1.** Here is the Accordion definition in XAML and C#:` |
| Low | Prose sentence with 26–40 words after syntax exclusions | 787 | 495 | `_assetsApi/api/index.md:94` — sentence beginning “The API reference section…” |
| Medium | Prose sentence with more than 40 words after syntax exclusions | 25 | 23 | `controls/barcode/2d-barcodes/qrcode-overview.md:15` — sentence beginning “A QR code consists…”; JSONL includes `word_count` |
| Low | Selected complex vocabulary or a sentence-starting indirect instruction | 63 | 62 | `controls/aiprompt/commands-events.md:12` — “commands that you can utilize” |
| Low | Actual code immediately after a heading, without intervening prose | 32 | 12 | `controls/datagrid/columns/width.md:45` — opening XAML fence |
| Low | Raw URL used as a link label | 6 | 4 | `installation/manual-installation-approaches/nuget/nuget-troubleshooting.md:34` |
| Medium | Legacy colon/bold admonition label instead of designated callout syntax | 5 | 5 | `security/overview.md:65` — `>Note: Our definition of "Done"…` |
| Low | Unlinked URL in prose | 1 | 1 | `knowledge-base/nuget-error-maui-check-tool.md:45` — `https://api.nuget.org/v3/index.json` |

Prefer native ordered lists, shorter direct sentences, meaningful destination labels, introductory sample prose, and the site's designated callout syntax. The vocabulary/instruction screen is intentionally narrow: relative clauses such as “information you need to…” and conditional clauses such as “unless you need to…” are not counted as indirect instructions.

### Human-review queue

| Review category | Cases | Unique articles | Review needed |
| --- | ---: | ---: | --- |
| Opaque included/snippet content | 651 | 651 | Inspect generated inclusions separately; 2,047 directive occurrences are grouped into article-level cases |
| Brief or topic-only alternative text | 338 | 236 | Determine image purpose and whether the alternative conveys essential information |
| Selected specialist acronym without detected expansion | 36 | 36 | Decide whether audience knowledge is sufficient or a first-use expansion is needed |
| Identical link label with different source targets | 18 | 11 | Decide whether destinations are equivalent or labels need qualification |
| Placeholder-like code notation | 5 | 3 | Verify explanations and consistent substitution conventions |
| Command sample without detected nearby outcome wording | 3 | 2 | Determine whether an expected result is relevant and adequately described |
| Heading transition across an opaque template inclusion | 2 | 2 | Inspect the expanded outline before changing source heading levels |
| Pipe-delimited table source not parsed as a GFM table | 1 | 1 | Check header/delimiter column counts at `controls/imageeditor/toolbar/styling.md:62` |

For example, `controls/barcode/1d-barcodes/specifications.md:19` contains a brief alternative requiring purpose review; no image pixels were examined. The apparent H1-to-H3 transitions at `installation/vs-integration/new-document-processing-wizard.md:18` and `installation/vs-integration/new-project.md:19` span template inclusions at lines 16 and 17 respectively, so they are review cases rather than confirmed heading violations.

### Scope and inventory reconciliation

The original recursive inventory contains **1,416 Markdown files** (`.md` or `.markdown`, case-insensitive), including `.github` metadata paths without reading agent-definition contents. There are no `.markdown` files. After adding this report, the physical Markdown count is **1,417**: **1,370 scored + 47 excluded**. `scores.jsonl` is also explicitly excluded as an audit artifact, but is not a Markdown file and therefore does not increase either Markdown inventory count.

The exclusions below are mutually exclusive, applied in the listed order. Counts refer to files, not directories; zero categories are shown explicitly.

| Exclusion category | Original inventory | After outputs | Rule |
| --- | ---: | ---: | --- |
| Audit outputs and audit-output directories | 0 | 1 | Exclude `accessibility-report.md`, `scores.jsonl`, and audit-output directories; only the report is Markdown |
| `.git` metadata | 0 | 0 | Not article content |
| `.github` metadata | 15 | 15 | Authoring/automation metadata, not published articles |
| `node_modules` | 0 | 0 | Dependency content |
| `_site` | 0 | 0 | Generated site output |
| `bin` | 0 | 0 | Build output |
| `obj` | 0 | 0 | Build intermediates |
| Configured excluded filenames | 2 | 2 | `_config.yml:6` and `docs-builder.yml:26–28`; `README.md` and `copyright.md` at any depth |
| Configured `controls/chart/how-to` | 0 | 0 | `_config.yml:6`; directory has no Markdown files |
| Non-article `_contentTemplates` fragments | 18 | 18 | Reusable `#region`/`#end`-style fragments and template directives, not standalone articles |
| Unpublished frontmatter | 11 | 11 | Case-insensitive `publish: false` or `published: false` YAML boolean |
| Generated API Markdown excluded by configuration | 0 | 0 | No applicable configured exclusion or generated reference Markdown found |
| **Total excluded Markdown** | **46** | **47** | **Source article denominator remains 1,370** |

`exclude_navigation: [knowledge-base/*]` changes navigation, not publication eligibility. Of 275 knowledge-base files, 274 are included; only `knowledge-base/trial-message.md` is explicitly unpublished. `_assetsApi/api/index.md` is an included, hand-authored API landing article, not generated API reference output. No path is excluded merely because it contains “api”.

Exact excluded paths follow; metadata and filename exclusions take precedence over frontmatter, so unpublished `README.md` and `copyright.md` are counted only once.

**`.github` metadata — 15 paths:**

```text
.github/docs-agent/control-doc-author.agent.md
.github/docs-agent/control-doc-style.md
.github/docs-agent/control-doc-templates/README.md
.github/docs-agent/control-doc-templates/commands.md
.github/docs-agent/control-doc-templates/events.md
.github/docs-agent/control-doc-templates/feature.md
.github/docs-agent/control-doc-templates/getting-started.md
.github/docs-agent/control-doc-templates/methods.md
.github/docs-agent/control-doc-templates/overview.md
.github/docs-agent/control-doc-templates/styling.md
.github/docs-agent/control-doc-templates/visual-structure.md
.github/skills/accessibility-doc-optimization/SKILL.md
.github/skills/llm-doc-optimization/SKILL.md
.github/skills/seo-doc-optimization/SKILL.md
.github/skills/style-guide-scoring/SKILL.md
```

**Configured excluded filenames — 2 paths:**

```text
README.md
copyright.md
```

**Reusable authoring/include templates — 18 paths:**

```text
_contentTemplates/common/ai-coding-assistant.md
_contentTemplates/common/collectionview.md
_contentTemplates/common/extension.md
_contentTemplates/common/listview-obsolete.md
_contentTemplates/common/manual-packages.md
_contentTemplates/common/net-version.md
_contentTemplates/common/nuget.md
_contentTemplates/common/see-also.md
_contentTemplates/common/supported-platforms.md
_contentTemplates/common/telerik-cli.md
_contentTemplates/common/trial-package-deprecation.md
_contentTemplates/controls/ai-data-operations.md
_contentTemplates/controls/autocomplete.md
_contentTemplates/controls/charts.md
_contentTemplates/controls/datagrid.md
_contentTemplates/controls/inputview.md
_contentTemplates/controls/toolbar.md
_contentTemplates/get-started.md
```

**Explicitly unpublished frontmatter — 11 paths:**

```text
ai/copilot-extension.md
controls/pdfprocessing/overview.md
controls/richtexteditor/localization.md
controls/slideview/control-template.md
controls/spreadprocessing/overview.md
controls/spreadstreamprocessing/overview.md
controls/wordsprocessing/overview.md
controls/ziplibrary/overview.md
get-started/first-steps-vs-code.md
get-started/first-steps-vs.md
knowledge-base/trial-message.md
```

The only additional excluded Markdown path after generation is `accessibility-report.md`; the non-Markdown output is `scores.jsonl`. No documentation source or site configuration was changed.

### Operational scoring method

Existing `markdown-it-py` 3.0.0 (CommonMark with GFM tables), PyYAML 6.0.1, and Python's HTML parser were used without adding dependencies. Parser source maps preserve original, one-based line numbers. Frontmatter is masked without removing lines; trailing frontmatter whitespace is ignored for parsing, including the tab after `position: 4` in `controls/barcode/2d-barcodes/datamatrix-overview.md`. `integrations/document-processing-libraries.md` requires an explicit **Windows-1252 fallback after UTF-8 decoding fails**; its record identifies that encoding. No undecodable bytes were silently replaced.

For each dimension, `signal_count` is the number of scored source observations, including only human-review candidates with `affects_score: true`. `scoring_denominator` is the number of relevant opportunities, with a minimum of one: headings, images, parsed links, screened prose sentences, tables, prose blocks for formatting, callout labels, and code blocks respectively. Apply the following rules in priority order:

| Score | Reproducible rule |
| ---: | --- |
| 5 | No scored source signals; also the required default when the content type is absent |
| 1 | At least eight signals, and signals are at least half the dimension's scoring denominator |
| 2 | Otherwise, any confirmed High/Critical signal, or at least four scored signals |
| 3 | Otherwise, any Medium signal, or two to three scored signals |
| 4 | Otherwise, exactly one Low or scored human-review signal |

The rule order matters: widespread signals receive the first applicable lower score. The mapping is a **source-screening operationalization** of the eight-dimension rubric, not a calibrated measure of reader success. In particular, a low alternative-text score can reflect numerous unresolved short-alt candidates, **not** confirmed inaccessible images. Review-only uncertainty that does not establish a scored signal has `affects_score: false` and does not lower a score.

Every dimension includes a rationale of at most two sentences and concrete violations where detected. A score of 5 means **no flagged signal in the checks actually performed**, not that subjective or unsupported checks were automatically verified. The detailed fields permit recomputation without interpreting rationale prose.

### Checks performed and explicit limitations

| Dimension | Source checks performed | Not established by this screening |
| --- | --- | --- |
| Headings | Source H1 count; sequential levels; narrowly generic labels; empty labels and immediately empty peer/ancestor sections. KB `title` plus `res_type: kb` supplies the article title convention. Code/preprocessor lines are not headings. | Descriptiveness in context, visual-emphasis intent, child-only section appropriateness, or navigation after opaque expansion |
| Alternative text | Markdown/reference-image and HTML alternatives; missing/empty, generic, filename-like, brief/topic-only, unusually long and repeated adjacent-text candidates. Explicit decorative HTML markers are recognized. | Image purpose, visual equivalence, essential diagram detail, appropriate complexity/length, and whether decoration or repetition is appropriate; no pixels inspected |
| Links | Inline/reference/HTML links and Liquid slug destinations; generic labels, URL labels, unlinked prose URLs; exact same-label/different-target candidates. Equivalent Liquid whitespace spellings share a target. | Near-identical label consistency for the same destination, semantic destination equivalence, link validity, and rendered accessible names |
| Tables | GFM delimiter-defined headers without requiring bold; HTML `th`, including KB row headers; empty cells; missing immediate prose lead-in for tables with at least five columns; image-containing and unparsed pipe-table review | Full complex-header association, layout intent, and whether prose/list presentation would be more suitable |
| Plain language | Sentence-length signals after excluding inline code, destinations, tables, metadata and directives; selected “utilize” forms and sentence-starting “you need to” wording; selected acronym expansion candidates | Flesch–Kincaid grade level, comprehensive jargon/abbreviation definitions, grammatical passive voice, or nuanced active/imperative phrasing |
| Formatting | Visual pseudo-lists, bold-only admonition labels, non-link HTML underlines, and selected color-reference candidates | Rendered contrast, visual styling, and whether color/formatting is the sole information channel |
| Callouts | Designated `>note`, `>warning`, `>important`, `>tip`, `>caution` syntax; legacy labels; empty/context-dependent content; narrow destructive-consequence and density candidates | Complete semantic severity/type matching, full sentence completeness, and whether callouts are genuinely exceptional or overused |
| Code | Actual backtick/tilde opening fences, including list indentation; nonempty language information with additional metadata accepted; indented code recognized; heading-adjacent introduction gaps; selected placeholder/outcome candidates | Comprehensive shared-introduction coverage, placeholder explanation/consistency, command-result relevance, and all product/code correctness |

The screened source contains 1,160 images, 7,928 parsed links, 473 GFM tables, 24 HTML tables, 1,780 actual fenced blocks, and 342 designated callout labels. Fenced-code closing delimiters are **not** counted as unlabelled openings. Indented code does not incur a missing-fence-language penalty.

Sentence screening counts alphabetic words, allowing internal apostrophes/hyphens; sentence boundaries use punctuation followed by whitespace or paragraph end, with selected common abbreviations protected. Physical list-item boundaries are preserved even when the Markdown parser treats indented items as lazy paragraph continuation; pipe-table source lines are excluded from prose. This is a reproducible heuristic, not a linguistic readability verdict. Selected acronym review covers MVVM, CRUD, AOT, MSI and GAC rather than claiming comprehensive jargon detection.

Snippet/include directives, including `<snippet .../>`, Liquid includes and `@[template](...)`, are **opaque**. They are never expanded or penalized for lacking a language tag. Excluded reusable template content is **not assessed or attributed to embedding articles**: this is an explicit source-only blind spot, including any images, tables, headings or code that expansion might introduce. Runtime, keyboard, screen-reader, mobile, contrast, multimedia-alternative, and rendered accessibility behavior were not tested.

Severity is independent of score. Critical is reserved for a confirmed essential-access blocker, never a generic/empty-alt heuristic. Repeated confirmed source heading skips, HTML data tables without any `th`, and at least two actual unlabelled fenced blocks are High candidates; isolated heading skips or unlabelled fences are Medium. Ambiguous purpose/context remains Human Review Required with null severity. No such confirmed High/Critical case was detected in this source snapshot.

### Validation

- Reconciled the complete recursive inventory and all mutually exclusive exclusions; checked the included API landing and KB metadata-title convention.
- Recomputed every dimension's signal-based score, every weighted article value, all dimension means, and the overall mean from exact integer/decimal arithmetic; checked JSONL ordering, uniqueness, schema, evidence line bounds and source evidence.
- Executed **28 regression assertions across 16 in-memory fixtures plus real-source checks**, covering reference images/links, Liquid target equivalence, canonical callouts, actual opening-fence counting, nested/list and tilde fences, indented code, `#endif`, opaque directives, heading-skip severity, explicit decoration, HTML row headers, GFM headers/empty cells, malformed tables, lazy list/sentence boundaries, genuine long sentences, formatting signals, and case-insensitive unpublished booleans. No test/helper files or dependencies were added.
- Sampled original article evidence for every detected Medium/Low pattern and the known parser edge cases, including `knowledge-base/customize-chart-tooltip-net-maui.md:51`, `ai/mcp-server.md:184`, and the two opaque-template heading transitions.
- Confirmed that the two short prose sentences and separate list options at `controls/toolbar/items/label.md:40–44` and `controls/imageeditor/toolbar/styling.md:73–77` are not merged or flagged as one long sentence; the separate malformed table at the latter article's line 62 remains a human-review case.
- Validation establishes inventory/arithmetic/source-screening consistency, **not** semantic accessibility or conformance. No documentation sources, configuration, or product code were modified.

## Critical and High Issues

**No confirmed Critical issues. No confirmed High issues.** There are no affected articles to group; pending human-review cases must not be read as cleared issues.

| Severity | Article | Line | Dimension | Issue | Recommended Fix |
| --- | --- | --- | --- | --- | --- |
| — | — | — | — | No confirmed Critical or High source finding | Resolve the separately recorded Human Review Required cases through appropriate semantic/rendered review |
