---
name: style-metadata-links
description: "Use this skill when writing or reviewing Telerik UI for .NET MAUI article metadata, control taxonomy, navigation, slug cross-references, external links, SEO descriptions, or sample-app pages. Covers title, page_title, description, slug, components, tags, position, redirects, and KB metadata. Use when asked to 'fix metadata', 'add frontmatter', 'check links', 'improve SEO', or 'review descriptions' in MAUI documentation."
---

# Metadata, Cross-References, and Links

This skill defines how to write YAML frontmatter metadata, create cross-references, format links, and structure sample-app pages in Telerik UI for .NET MAUI documentation. The [build configuration](../../../../docs-builder.yml) identifies the product as Telerik UI for .NET MAUI and the documentation path as `/maui-ui/documentation`.

## YAML Frontmatter Metadata

Every documentation article starts with a YAML frontmatter block delimited by `---`. The metadata controls SEO, navigation, and site generation.

> **Editing restriction**: During routine optimization of existing articles, edit only `description` by default and report other metadata defects. An explicit request to migrate metadata or taxonomy authorizes the named fields; preserve stable URLs, redirects, and navigation unless their migration is also requested. The other field rules below guide new articles and authorized metadata corrections.

### Required Fields

| Field | Purpose | Rules |
|-------|---------|-------|
| `title` | Display title in navigation and breadcrumbs | Title case; may be a short label such as Getting Started or Data Binding. A standard article's single descriptive H1 must cover the same topic, not necessarily repeat this label verbatim. KB articles use metadata for the title and must not contain an H1. |
| `page_title` | HTML `<title>` tag for SEO | Follow neighboring MAUI pages, for example `.NET MAUI DataGrid Documentation - Getting Started`; identify the control or product without trademark symbols. Do not invent a `meta_title` field. |
| `description` | HTML meta description for search engines | Between 120 and 150 characters; must be a complete, meaningful sentence; include primary keywords naturally |
| `slug` | Unique URL identifier for the article | New slugs are lowercase and hyphen-separated; all slugs must be unique across the site. Preserve exact historical identifiers unless URL migration is authorized. |

### Optional Fields

| Field | Purpose | Rules |
|-------|---------|-------|
| `tags` | Categorization tags for search and filtering | Comma-separated, lowercase |
| `position` | Sort order in navigation (lower = higher in list) | Integer; articles without position appear alphabetically after positioned ones |
| `previous_url` | Redirect from a former URL after article moves | Full path starting with `/`; keeps old bookmarks working |
| `components` | Product or control taxonomy | YAML array of existing identifiers, for example `["datagrid"]`, `["collectionview"]`, or `["general"]`; verify against neighboring pages |
| `type` | KB article classification | Use the repository's `how-to` or `troubleshooting` convention; follow the approved template for a security advisory |
| `res_type` | KB resource classification | Use `kb` on Knowledge Base articles |
| `ticketid` | Optional support traceability | Follow repository policy; do not expose private support content or invent a ticket ID |

### Metadata Examples

```yaml
---
title: Data Binding
page_title: .NET MAUI CollectionView Documentation - Data Binding
description: "Learn how to bind the Telerik UI for .NET MAUI CollectionView to a collection, set its binding context, and display item data."
slug: collectionview-data-binding
components: ["collectionview"]
tags: .net maui, collectionview, data binding
position: 3
---
```

### Description Writing Rules

The `description` field is critical for SEO and search result snippets. Follow these rules:

1. **Minimum 120 characters** — Shorter descriptions do not meet the repository metadata standard.
2. **Maximum 150 characters** — Aim near this limit without padding. Search engines can rewrite or truncate snippets; length does not guarantee their appearance.
3. **Complete sentence** — Write a full sentence, not a fragment or keyword list.
4. **Include primary keywords** — Mention the main topic and product name naturally.
5. **Unique per article** — Every article must have a distinct description. Do not reuse descriptions across articles.
6. **Valid YAML and plain text** — Quote scalars containing YAML-sensitive punctuation and escape embedded quotes correctly. Do not put HTML, Markdown, code fences, or trademark symbols in SEO metadata; C# and .NET are valid topic terms.
7. **Action-oriented** — Start with "Learn how to...", "Discover...", or describe what the reader will accomplish.

| ❌ Bad descriptions | ✅ Good descriptions |
|---|---|
| CollectionView binding | Bind a collection to the Telerik UI for .NET MAUI CollectionView, configure its binding context, and display item data in your app. |
| This article describes styling. | Customize the Telerik UI for .NET MAUI DataGrid with styles and resource dictionaries, and configure the appearance of cells and headers. |
| (empty) | Learn how to add the Telerik UI for .NET MAUI TreeView to your app, bind hierarchical data, and configure item selection and expansion. |

## Cross-References and Links

Links connect articles and help readers navigate the documentation. Well-crafted links improve both usability and SEO.

### Internal Links — Slug Syntax

Use the Jekyll slug syntax for internal links between documentation articles:

```markdown
For more information, see [binding a CollectionView to data]({%slug collectionview-data-binding%}).
```

This syntax resolves the slug to the correct URL regardless of the article's file location, making links resilient to file moves.

### Anchor Text Rules

Anchor text (the visible text of a link) must be **descriptive and self-explanatory**. A reader should understand what they will find at the link destination without reading the surrounding text.

| ❌ Bad anchor text | ✅ Good anchor text |
|---|---|
| Click [here](...) for more information. | See [DataGrid setup](...) for prerequisites. |
| Read [this article](...) to learn more. | Read [CollectionView data binding](...) for details. |
| For details, see [link](...). | For details, see [the RadDataGrid API reference](...). |
| [More info](...) | [TreeView selection options](...) |

### Paraphrase Article Titles

Use descriptive anchor text that fits the surrounding sentence. Paraphrase long titles when useful; exact article titles are acceptable, especially in navigation and See Also lists. Never sacrifice clarity or API accuracy to force variation:

```markdown
See [how to set up the DataGrid]({%slug datagrid-getting-started%}).
See [Getting Started with the .NET MAUI DataGrid]({%slug datagrid-getting-started%}).
```

### Varied Anchor Text

Use consistent names for the same control and destination. Natural contextual variation is acceptable, but repeated accurate anchor text is not an SEO defect. Link quality and reader orientation take priority.

```markdown
First occurrence: See [DataGrid setup]({%slug datagrid-getting-started%}) for prerequisites.
Second occurrence: Follow the [DataGrid getting-started guide]({%slug datagrid-getting-started%}) to add the control.
```

### External Links

External links (to URLs outside the documentation site) follow additional rules:

1. **Use HTTPS** — Always link to HTTPS URLs. If the target does not support HTTPS, reconsider whether the link is appropriate.

2. **Check for broken links** — Verify that external URLs are live and point to relevant content. External URLs change; review them periodically.

3. **Choose the correct product and version** — Prefer Telerik UI for .NET MAUI documentation and API pages or Microsoft .NET MAUI documentation. Use Document Processing documentation only for a library scenario; do not substitute another Telerik UI suite's APIs.

4. **Preserve normal link behavior** — Do not require `target="_blank"`. Let the site renderer control external-link behavior; if a new window is required, disclose it accessibly and follow site policy.

### Navigation and Link Validation

Resolve every slug to an existing article and verify any fragment against a real heading or explicit anchor. Scan the site for duplicate slugs when adding or changing one. For a new control article, check `components`, `position`, the neighboring `_meta.yml` if present, and folder metadata in `docs-builder.yml`; do not assume frontmatter alone places the page correctly.

Use slug links in published articles. Relative paths are appropriate for images and for links between these skill files. Keep intentional migration redirects and exact historical identifiers; do not normalize them mechanically. Check links to Getting Started, control overview, feature pages, and See Also destinations for the same control family. State which external URLs could not be checked.

### Link Placement Rules

- Place links inline in the text where they are most relevant.
- Do not cluster multiple links in a single sentence — spread them across the section.
- Collect related links in a "See Also" section at the end of the article.
- Do not place links in headings.

## Demo and Sample-App Articles

MAUI sample-app articles describe runnable applications such as SDKBrowser or Controls Showcase, not browser-only demos. Follow the [SDKBrowser article](../../../../demos-and-sample-apps/sdkbrowser-app.md) and link to the relevant control feature pages.

### Demo Metadata

- **Unique meta descriptions** — Each demo page must have its own description, different from the feature article description.
- **Keywords** — Include relevant keywords in the description that match how users search for the feature.

### Demo Content

- **Descriptive introduction** — Start with a brief description of what the demo demonstrates.
- **Links to feature documentation** — Include links to the corresponding feature article(s) for readers who want to learn more.
- **Working examples** — Ensure all demo code compiles and runs correctly.
- **Platform and version context** — Identify the sample source, Telerik and .NET versions, target platform, setup, and navigation path within the app. Do not claim a browser preview proves native behavior.

## Quick Checklist

When reviewing an article for metadata and links, verify:

- [ ] All four required metadata fields are present: `title`, `page_title`, `description`, `slug`
- [ ] Navigation `title`, descriptive H1 or generated KB title, and `page_title` describe the same MAUI topic
- [ ] The `description` is between 120 and 150 characters, a complete sentence, and unique
- [ ] New slugs are lowercase and hyphen-separated; all slugs resolve uniquely
- [ ] Existing URL identifiers and redirects remain stable unless their migration is authorized
- [ ] Control `components`, MAUI tags, KB `type`/`res_type`, and navigation metadata use existing taxonomy
- [ ] YAML parses, descriptions contain plain text, and SEO metadata omits trademark symbols
- [ ] Internal links use the `{%slug ...%}` syntax
- [ ] Anchor text is descriptive (no "click here", "this article", "link")
- [ ] Anchor text is accurate and consistent; paraphrasing or variation is optional
- [ ] Slugs, fragments, relative assets, and external destinations resolve to the intended MAUI content
- [ ] Platform and version references match the article; unverified external URLs are disclosed
- [ ] No links inside headings
- [ ] "See Also" section at the end with related links
