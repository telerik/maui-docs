# Telerik MAUI Docs — Style & Conventions

Source of truth: <https://testdocs.telerik.com/style-guide> and <https://github.com/telerik/maui-docs/wiki>.
This file captures the rules that the **Control Doc Author** agent must enforce. When the
style guide and this file disagree, the style guide wins — update this file in the same PR.

## Voice & tone

- Address the reader as **you**. Never use *we*, *our*, *us*, *I*.
- Prefer the active voice and present tense. "The Calendar exposes…" not "The Calendar is exposing…".
- Be factual and task-oriented. No marketing adjectives ("powerful", "amazing", "blazing fast").
- No emoji. No exclamation marks. Only safe contractions are allowed (`aren't`, `can't`, `don't`, `doesn't`, `haven't`, `didn't`, `shouldn't`, `couldn't`); never use `you'll`, `it's` (for "it has"), `that's`, `there's`, `who's`.
- Capitalize the product name as **Telerik UI for .NET MAUI** and the control as **.NET MAUI <Control>** in titles.
- Do not use "simply", "easy", "please note", "at this time", or "let's" (except in getting-started articles). Avoid vague qualifiers such as "good" or "best" without objective support.
- Do not use Latin abbreviations (`e.g.`, `i.e.`, `etc.`). Write "for example", "that is", "and so on".
- Use American English spelling, present simple tense, and imperative mood for instructions. Use `must` or `need to` for obligations; avoid ambiguous `should`/`could`/`would`.
- Keep sentences to 25 words or fewer and paragraphs to two to four sentences. Rephrase `there is`/`there are` when a stronger subject is available.
- Prefer simple words (`use`, not `utilize` or `leverage`).
- Expand every acronym and abbreviation on first use in each article, for example "Extensible Application Markup Language (XAML)". Do not expand product names such as SDKBrowser; describe them instead ("the SDKBrowser Demo Application").
- Use one term per concept throughout the article (for example, always "control", never alternating with "component" or "widget"). Keep prose terms identical to code identifiers.
- Use gender-neutral language. Avoid idioms, slang, metaphors, and culture-specific references.

### Vocabulary

- Use `checkbox`, `click X`, `tap X`, `hover over`.
- Use `unavailable` instead of `disabled` or `grayed out` for UI state in prose (keep `IsEnabled` and other API names as they are).
- Use `earlier`/`later` for versions and `starting with` instead of `since` or `as of`.
- Write **C#** and **VB.NET** in prose and code-block tags. Never write "csharp", "CSharp", "vb", or "Visual Basic".

### Numbers and punctuation

- Spell out zero through nine unless the number is a version, product name, API value, or appears in a table. Use digits for 10 and above.
- Do not start sentences, headings, or captions with a numeral.
- Use an en dash (`&ndash;`) without spaces for ranges, for example `1&ndash;15`.
- Use the serial (Oxford) comma in series of three or more items.
- Use a comma after "for example" and "that is" when they introduce a clause.

## Front matter (every article)

```yaml
---
title: <Same text as the H1>                        # Title Case, distinct from sibling articles
meta_title: <Control> <Topic> - Telerik UI for .NET MAUI   # Topic first, 40-70 chars
description: <One complete, action-oriented sentence, 100-150 chars, ends with a period>
position: <int>                                     # See ordering below
tags: <comma list>                                  # optional; lower case
slug: <control>-<article>                           # kebab-case, globally unique
previous_url: <old slug>                            # optional, only when migrating
---
```

Front matter rules:

- `title` must match the H1 exactly (or differ only in casing) and must not be a generic label such as `Overview` or `Events` on its own.
- `meta_title` must lead with the most specific term (control + topic) and end with the product name. Keep it within 40&ndash;70 characters. Do not repeat keywords. Always use `meta_title` (not `page_title`) in new articles.
- `description` is a hard 100&ndash;150 characters, never longer. It must state what the reader learns or accomplishes, include the control and feature name, start with an action verb such as "Learn how to" or "Discover", and be unique across sibling articles. No marketing phrasing ("Try now", "powerful").
- `slug` uses lowercase letters and hyphens only, three to six words, no repeated words.
- Add `previous_url` when the article replaces a moved or renamed article.

Ordering (`position`) inside a control folder:

| Article             | position |
|---------------------|----------|
| overview.md         | 0        |
| visual-structure.md | 1        |
| getting-started.md  | 2        |
| configuration / first feature | 3 |
| further features    | 4, 5, …  |
| events.md           | last - 1 |
| methods.md          | last - 2 |
| commands.md         | last - 3 |
| styling.md          | last     |

## Headings

- Each article starts with a single H1 in the form `# .NET MAUI <Control> <Topic>`.
- Use H2 (`##`) for sections, H3 (`###`) for subsections. Do not skip levels.
- No trailing punctuation in headings.
- Use Title Case: capitalize nouns, verbs, adjectives, adverbs, and pronouns; lowercase articles, coordinating conjunctions, and prepositions unless they are the first or last word.
- Headings must be descriptive and task-oriented so a reader can navigate by the heading outline alone. Avoid generic labels such as `Example`, `Details`, `More Info`, or `Notes`. Prefer headings that mirror search queries, for example `## Set the Increment Step`.
- Use the same verb form for every action heading in an article. Use the imperative form (`Configure the Feed`), not the gerund (`Configuring the Feed`).
- The first sentence under a heading directly answers or defines the heading topic.
- Every heading has content below it; no empty sections. Every `##` section has at least two or three sentences or a meaningful list/example and stays under about 450 words; split longer sections into `###` subsections.
- Do not use API member names in conceptual headings. Member names are allowed in API-reference headings (events, methods).
- Reserve `## See Also` for the final section.

## Links

- Internal links use Jekyll slug syntax: `[Text]({% slug control-feature %})`.
- Link text describes the destination. Never use `click here`, `here`, `this article`, `more`, or bare URLs.
- Use the same anchor text for links to the same destination, and never use the same anchor text for different destinations.
- Introduce external links with a sentence that explains what the linked page contains, and open them in a new tab where HTML syntax is available (`<a href="..." target="_blank">`).
- Overview articles link to every feature article (hub-and-spoke). Feature articles link to related features and prerequisites in context, not only in See Also.
- Do not hard-code `https://docs.telerik.com/...` for in-repo articles.

## Self-contained sections

Each section must make sense when read alone (as a search result or retrieved chunk).

- Do not write "see above", "see below", "as mentioned earlier", or "now that you have configured". Link to the section by name or anchor instead.
- Every pronoun has a clear antecedent in the same section. Repeat the control name rather than writing "it" at the start of a section.
- State prerequisites at the top of the section that needs them.

## Content depth

- Aim for at least 300 words in feature, getting-started, and overview articles.
- Explain why and when to use a feature or setting, not only how.
- Document known limitations, unsupported platforms, and common errors in a `## Known Limitations` or `## Troubleshooting` section when they exist. Never invent them; ask the user.
- Show the expected result (screenshot, output, or success criteria) for each procedure.
- Do not copy introduction paragraphs verbatim between sibling articles.

## Lists and tables

- Introduce every list with a sentence that ends with a colon. The link list under `## See Also` is the only exception.
- Start every item with an uppercase letter and keep items grammatically parallel. Either all items end with a period or none do (all do if any item is a full sentence).
- Use numbered lists for sequential steps and bulleted lists for unordered items. Do not create single-item lists. Nest no deeper than three levels.
- Indent content (snippet tags, code blocks, images) that belongs to a numbered step so the numbering continues correctly.
- Definition lists use `&mdash;` with no surrounding spaces.
- Tables have a header row, no empty cells (use `N/A` or `None`), and a lead-in sentence. Do not use tables for layout.

## Callouts

Use only the platform callout syntax and match it to severity:

- `> note`&mdash;Supplemental information.
- `> tip`&mdash;Helpful pointers, including the SDKBrowser cross-reference.
- `> important`&mdash;Required actions.
- `> caution`/`> warning`&mdash;Risk of data loss or breaking behavior.

Every callout contains at least one complete sentence that makes sense on its own. Do not use bold text alone to signal a warning, and do not overuse callouts.

## Formatting

- Bold (`**...**`) only UI elements (buttons, menus, tabs, dialog names). Do not use bold or all-caps for emphasis.
- Use backticks for code elements, file names, paths, values, types, and user input.
- UI navigation paths use bold labels separated by ` > `, for example **File** > **New**.
- Keyboard shortcuts use Initial Caps joined with `+` without spaces, for example `Ctrl+C`.
- Do not convey meaning by color alone.

## Code & snippets

- Runnable XAML / C# samples live in the SDKBrowser repo and are referenced via:
  `<snippet id='<control>-<feature>[-xaml|-csharp]' />`
- Inline fenced code blocks are allowed only for:
  - The `xmlns:telerik` declaration.
  - `MauiProgram.cs` `UseTelerik()` registration.
  - Resource dictionaries / styles when shown as configuration, not as a runnable sample.
  - Short property/value tables (prefer Markdown tables instead).
- Every fenced code block has a language tag (` ```XAML `, ` ```C# `, ` ```VB.NET `, ` ```json `, ` ```bash `).
- Introduce every code block and snippet tag with a sentence that explains what it contains.
- Mark placeholders consistently as `<placeholder>` and explain what to substitute.
- Always show a screenshot or animated GIF after a "what does it look like" example. Place images under `controls/<control>/images/` with descriptive kebab-case names.

## Images & alt text

Every image must have a detailed, meaningful description so that readers using assistive technology, search engines, and LLMs understand what the image shows.

- **Alt text** (the `![...]` part) must describe what is visible, not just repeat the control name. Include:
  - The control and the feature or state being demonstrated (for example, expanded, selected, filtered, disabled).
  - Key visible elements and their arrangement (for example, header, items, buttons, indicators).
  - Relevant data or values shown, when they help understanding.
  - The platform or theme, if it matters for the example.
- Keep alt text to one or two sentences (roughly 80&ndash;200 characters). Do not start with "Image of" or "Screenshot of".
- **Title** (the quoted text after the path) is optional; when used, it must add information beyond the alt text, not duplicate it.
- For animated GIFs, describe the interaction sequence (for example, "User taps the drop-down arrow, the list opens, and the second item is selected").
- When an image conveys information that is not stated in the surrounding text, add a short sentence before the image explaining what the reader should notice.
- Never use placeholder alt text such as `.NET MAUI {{ControlName}} Overview` without a descriptive suffix.
- Do not repeat the surrounding caption or paragraph verbatim in the alt text.
- Mark purely decorative images with empty alt text (`![](...)`).
- Captions, when used, are bold, descriptive, in sentence case, and placed before the image.
- Screenshots use the default (light) theme and never show sensitive or confidential data.

Examples:

```markdown
<!-- Avoid -->
![.NET MAUI ComboBox Overview](images/combobox-overview.png)

<!-- Prefer -->
![.NET MAUI ComboBox with an open drop-down list showing five city names, the second item highlighted as selected, and a search text box at the top](images/combobox-overview.png)
```

## API descriptions

When listing properties, events, commands, templates use the bullet pattern:

```markdown
* `MemberName`
```

- Use `&mdash;` (em dash) between the signature and the description.
- Type appears in backticks and is fully qualified the first time it is mentioned in the article.
- Sentences end with a period.

## SDKBrowser cross-reference

Every getting-started, feature, styling, commands, and methods article ends its main content with a `tip` callout:

```markdown
> tip For a runnable example with the <Control> <Feature> scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **<Control> > <Category>** category.
```

Where `<Category>` is `Getting Started` for the getting-started article and `Features` for feature articles.

## Mandatory sections per article type

| Article          | Required sections                                                                 |
|------------------|-----------------------------------------------------------------------------------|
| overview         | Lead paragraph, screenshot, Key Features bullet list, Next Steps, See Also       |
| visual-structure | Lead, anatomy image, Displayed Elements list, See Also                            |
| getting-started  | Lead, default-look image, Prerequisites, Define the Control (numbered steps), SDKBrowser note, Additional Resources, See Also |
| feature          | Lead, API list, task-oriented example section with numbered steps + snippet tags, screenshot, SDKBrowser tip, Known Limitations (when applicable), See Also |
| styling          | Lead, properties list, task-oriented example section, screenshot, SDKBrowser tip, See Also |
| commands         | Lead, list of commands with parameter types, task-oriented example section, SDKBrowser tip, See Also |
| events           | Lead, per-event H2 with handler signature + snippet examples, See Also            |
| methods           | Lead, per-method H2 + snippet examples, See Also                                 |

## Common pitfalls to reject

- Inline 30-line XAML/C# samples instead of `<snippet />` tags.
- Missing `slug:` or duplicated slug.
- `position` collisions inside a folder.
- "We" / "let's" / first person.
- `description` outside the 100&ndash;150 character range or `meta_title` outside 40&ndash;70 characters.
- Generic headings (`Example`, `Overview`) or a `title` that does not match the H1.
- Plain `>` blockquotes used as callouts.
- Unlabeled code fences or images with non-descriptive alt text.

## Quality gate (scoring skills)

Before reporting an article as done, score it with each skill under `.github/skills/`:

| Skill | Focus | Minimum overall score |
|-------|-------|-----------------------|
| `style-guide-scoring` | Progress DevTools Style Guide | 4.0 |
| `seo-doc-optimization` | Metadata, keywords, search intent | 4.0 |
| `accessibility-doc-optimization` | Headings, alt text, links, plain language | 4.0 |
| `llm-doc-optimization` | Structure, self-contained sections, terminology | 4.0 |

No single dimension may score below 3. Fix the reported violations and score again. If a violation cannot be fixed without information you do not have (for example, limitations or real data), report it to the user instead of inventing content.
- Feature article without an SDKBrowser sample reference.
- Adding a feature article but forgetting to update the parent `overview.md` Key Features list.
