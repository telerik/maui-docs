# Telerik UI for .NET MAUI Documentation Accessibility Audit

**Audit date:** October 21, 2026  
**Status:** Baseline review of repository source; not a conformance certification  
**Primary criteria:** [`accessibility-doc-optimization` skill](../skills/accessibility-doc-optimization/SKILL.md), which evaluates headings, alternative text, links, tables, plain language, formatting independence, callouts, and code blocks against WCAG 2.1 AA documentation practices.

## Executive summary

This review found useful accessibility material, including screen-reader instructions for CollectionView, keyboard-navigation guides for a subset of controls, semantic-property examples for Calendar, descriptive image text in many articles, and titled video embeds. The main risk is incomplete and difficult-to-discover accessibility guidance for developers building applications with the controls.

The source inventory contained 1,359 Markdown files outside `.github/`, including 997 files under `controls/` and 68 control folders. A source scan found:

- 12 control folders with an `accessibility/` directory (14 articles); four additional controls have keyboard guides outside that directory.
- Dedicated screen-reader instructions for one control, CollectionView.
- Two Calendar knowledge-base articles with `SemanticProperties` examples; no general semantic-properties guide was found.
- 13 articles with multiple Markdown H1 headings and 24 heading-level skips after an H1 in the scanned Markdown.
- 1,308 Markdown image references, all with non-empty alt text in the matched syntax. This does not prove that each description is an adequate equivalent.
- 1,762 fenced code blocks, with one opening fence lacking a language tag.
- Ten embedded iframe videos, all with a `title` attribute in source. Caption and transcript availability were not verified.
- Empty table cells in ten Markdown table lines, including examples where a default value or description is left blank.

These counts are source-pattern indicators, not a full WCAG evaluation of rendered pages. Detailed findings and remediation suggestions follow.

## Scope and method

The review used the repository skill as the authoritative checklist and searched the Markdown documentation across product controls, getting-started material, installation, knowledge-base articles, and other documentation areas. It combined corpus-wide pattern scans with manual review of representative control overviews, accessibility and keyboard articles, introductory content, knowledge-base examples, tables, charts, code, images, callouts, and video embeds.

The audit distinguishes documentation gaps from product behavior. An absent article does not establish that a control lacks an accessibility feature. No runtime behavior or product conformance was inferred from source text.

### Limitations

- The documentation site could not be loaded in the browser during this review. Rendered headings, HTML table semantics, focus order, keyboard operability of site navigation, color contrast, and screen-reader output remain unverified.
- The review did not test Telerik controls with TalkBack, VoiceOver, Narrator, or other assistive technology.
- Image alt text, captions, and transcripts were inspected only as represented in source; whether they convey equivalent information requires human review and, for videos, playback.
- No repository-wide reading-grade score was computed. A plain-language pass should be included in follow-up remediation.
- The review is a broad static baseline, not line-by-line editorial certification of every page.

## Findings

Severity describes the likely user impact of the documentation gap or content pattern, not the severity of a product defect.

### A1 — Screen-reader guidance is limited to one control

**Severity: High — product documentation gap**

`controls/collectionview/accessibility/screen-reader.md:13-32` describes screen-reader behavior for CollectionView and names TalkBack, VoiceOver, and Narrator. The inventory found no comparable dedicated screen-reader article for the other 67 control folders. The page also focuses its configuration example on WinUI automation, leaving readers without comparable control-specific examples for the other named platforms.

This does not establish that other controls are inaccessible. It means developers cannot use this documentation to determine expected announcements, accessible names and states, platform differences, or how to test those controls with a screen reader.

**Recommended action:** Publish a shared screen-reader/accessibility guide and add control-specific notes for high-use and complex controls, starting with Button, Entry, Editor, Calendar, DataGrid, TreeDataGrid, charts, and data-entry controls. For each, document supported platforms, accessible name/value/state behavior, customization APIs, known limitations, and a reproducible test procedure. Link each article from the relevant control overview.

### A2 — Keyboard guidance covers a subset of controls and is organized inconsistently

**Severity: Medium — discoverability and platform-coverage gap**

Keyboard guidance is split among several naming/location patterns: articles under `controls/<control>/accessibility/keyboard-navigation/`, `controls/<control>/keyboard-navigation/` (for example, DataGrid and TreeDataGrid), and `keyboard-support.md` (AutoComplete and ComboBox). The dedicated articles cover 16 control families; the control inventory has 68 folders. The dedicated keyboard guides reviewed describe WinUI and/or MacCatalyst behavior, not a cross-platform keyboard coverage matrix.

Examples include:

- `controls/collectionview/accessibility/keyboard-navigation/windows.md`
- `controls/datagrid/keyboard-navigation/windows.md`
- `controls/treedatagrid/keyboard-navigation/maccatalyst.md`
- `controls/autocomplete/keyboard-support.md`
- `controls/combobox/keyboard-support.md`

The separate locations make it harder to discover the full keyboard story from a control’s accessibility content. The absence of mobile keyboard guidance should not be read as a claim that the controls do not work with external keyboards or mobile assistive technology.

**Recommended action:** Provide a common accessibility index and use consistent links and metadata from each control overview. State platform coverage explicitly, distinguish keyboard navigation from touch and screen-reader behavior, and record unsupported or untested combinations rather than leaving the platform scope implicit.

### A3 — Semantic-property examples are Calendar-specific; no general authoring guide was found

**Severity: High — product documentation gap**

The repository has two Calendar-focused examples: `knowledge-base/set-semantic-properties-calendar-navigation-buttons.md:29-39` uses `SemanticProperties.Description`, and `knowledge-base/identify-current-selection-state-calendar-net-maui.md:29-65` binds a description to the Calendar display mode. The CollectionView screen-reader page documents its `AutomationManager`, but there is no general guide that explains how application authors should add semantic labels, hints, values, and state to Telerik control content and custom templates. A search of the documentation also found no `AutomationProperties` references.

The main product documentation search found no references to WCAG, Section 508, or ADA. This is a discoverability and guidance gap, not a finding that the product is non-compliant.

**Recommended action:** Add an introductory guide explaining the relevant .NET MAUI semantic APIs and when developers should use them with Telerik controls and custom templates. Include tested XAML/C# examples, platform-specific behavior, localization of accessible text, focus management, contrast/high-contrast considerations, and limitations. Avoid compliance claims unless they are validated and appropriately scoped.

### A4 — Multiple H1 headings and skipped heading levels disrupt the source outline

**Severity: Medium — documentation structure**

The static scan found 13 articles with more than one Markdown H1 and 24 transitions that skip a heading level after an H1. For example, `controls/accordion/overview.md:10,25` uses `#` for both the page title and “Next Steps”; `controls/autocomplete/overview.md:10,34` repeats that pattern. `controls/collectionview/commands.md:23` starts a subsection at H3 after the H1 without an H2.

The skill recommends one H1 and sequential heading levels so readers can navigate by heading outline. Some knowledge-base pages rely on frontmatter for the page title and intentionally begin their Markdown body with H2; those pages were not counted as heading skips in this finding.

**Recommended action:** Change section-level `#` headings such as “Next Steps” and “See Also” to `##`, and correct H1-to-H3 transitions to H2 where appropriate. Add a Markdown heading check that ignores YAML frontmatter and fenced code and accounts for the knowledge-base page-title convention.

### A5 — Empty table cells leave values and relationships unclear

**Severity: Medium — table comprehension**

The scan found empty cells in ten table lines. Examples include:

- `controls/aiprompt/localization.md:18-20` leaves the default value for `AIPrompt_CommandView_Header` blank.
- `controls/richtexteditor/working-with-images/insert-images.md:40-43` leaves descriptions blank for `Text` and `RichTextEditorFontSizeToolbarItem`.
- `controls/barcode/1d-barcodes/specifications.md:28-30` has several empty trailing cells for Code 128 subsets.
- `controls/speechtotextbutton/winui-support.md:29` contains an empty table cell.

Some empty values may be intentional, but the source does not explain whether they mean “none,” “not applicable,” or “not documented.” A screen-reader user navigating table cells receives no distinction.

**Recommended action:** Replace unexplained blanks with a meaningful value such as “None” or “Not applicable,” or remove columns that do not apply. Add descriptions where a table documents configurable properties, and retain a clear header row and lead-in sentence.

### A6 — Chart alt text describes appearance but not the data conveyed

**Severity: Medium — nonvisual access to visualizations**

`controls/charts/cartesian-chart/multiple-series.md:43-47` introduces a chart image and gives the alt text “combining red bars and a yellow line across quarterly categories.” This identifies visual marks and colors but does not provide the values, trend, or other chart takeaway in text. The surrounding article explains how to configure multiple series, not the information represented by this rendered chart.

**Recommended action:** Keep concise alt text for the image, and add a nearby textual summary of the important takeaway. Where users need exact values, provide the chart data in an accessible table or another text form. Do not make color the only way to identify a series.

### A7 — One fenced code block has no language annotation

**Severity: Low — isolated authoring issue**

`controls/toolbar/styling.md:45-47` contains an untagged fenced block with an XML namespace declaration. The source scan found one untagged opening fence among 1,762 blocks.

**Recommended action:** Label the block with its language (for example, `xml`) and keep the fence-language convention in the authoring checklist.

## Strengths and practices to retain

- The CollectionView screen-reader guide names platform screen readers and includes a configuration example.
- Several controls provide detailed keyboard key/action tables, including ComboBox and DataGrid.
- The Calendar knowledge-base articles demonstrate use of `SemanticProperties.Description` in real Telerik control scenarios.
- The 1,308 Markdown image references detected by the source scan all contain non-empty alt text. Representative overviews and demonstrations use descriptive alt text; equivalent-detail review is still needed for complex screenshots and charts.
- Link-text scans found no common “click here”/“here” patterns in documentation links.
- The single untagged code block indicates language annotation is already common in fenced examples.
- All ten iframe embeds found in Markdown have a `title` attribute, including `introduction.md:156` and `get-started/video-onboarding.md:20,25`.

## Follow-up validation items

These items require rendered-page or media testing and are not confirmed defects from the source audit:

1. Verify captions and, where useful, transcripts or equivalent text for the ten embedded instructional videos.
2. Test documentation-site keyboard navigation, focus visibility/order, search, landmarks, heading levels, and table semantics with keyboard and screen-reader combinations.
3. Review image equivalence for complex diagrams and screenshots, and verify that chart information is available as text or data.
4. Check rendered color contrast and whether any instructions depend on color, animation, or visual state alone.
5. Conduct a plain-language review of long or jargon-dense instructional passages.

## Suggested repository-wide authoring checklist

For new and updated articles:

- Use one descriptive H1, then use sequential heading levels for sections.
- Give each informative image contextual alt text; mark decorative images appropriately. For complex visuals, add a text equivalent or data table.
- Use link text that identifies the destination or action without relying on surrounding sentences.
- Give data tables a header row, explain complex tables before they appear, and do not leave meaningful cells blank.
- Tag every fenced code block with its language and introduce it with a sentence that explains its purpose.
- Use consistent, semantically appropriate note, warning, important, and tip syntax supported by the documentation renderer.
- Do not convey meaning through color, styling, or motion alone.
- For control guidance, document accessible names and states, keyboard and screen-reader interactions, platform differences, semantic APIs, localization, and known limitations.
- Verify the rendered article with keyboard and assistive technology before treating source checks as evidence of accessibility.

## Prioritized remediation backlog

| Priority | Follow-up task | Suggested starting area |
|---|---|---|
| High | Add discoverable, cross-platform screen-reader and semantic API guidance; document tested behavior for high-use controls. | CollectionView guidance as a model; Button, Entry, Editor, Calendar, DataGrid |
| High | Define and publish per-control accessibility coverage and platform behavior, including known gaps and how to test. | Control overviews and accessibility article locations |
| Medium | Fix multiple H1 headings and skipped levels, and prevent recurrence with a frontmatter-aware content check. | `controls/accordion/overview.md`, `controls/autocomplete/overview.md`, `controls/collectionview/commands.md` |
| Medium | Clarify empty table values and provide text equivalents for chart takeaways. | AIPrompt localization, RichTextEditor options, Barcode specifications, Cartesian chart examples |
| Medium | Standardize discoverability and cross-linking for keyboard and accessibility guidance. | AutoComplete, ComboBox, DataGrid, TreeDataGrid |
| Low | Add the missing code-fence language annotation. | `controls/toolbar/styling.md:45` |
| Validation | Test rendered site navigation, video captions, contrast, focus, and screen-reader output. | Public documentation site and embedded media |
