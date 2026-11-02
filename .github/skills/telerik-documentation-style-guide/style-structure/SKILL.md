---
name: style-structure
description: "Use this skill when structuring Telerik UI for .NET MAUI articles, headings, lists, and figures. Covers Getting Started, Installation, Fundamentals, control overviews, Data Binding, Commands, Styling, Templating, Events, Localization, Accessibility, Troubleshooting, and KB organization. Use when asked to 'fix headings', 'restructure the article', 'check list formatting', 'fix capitalization', or 'organize the content'."
---

# Article Structure, Headings, and Lists

This skill defines how to structure articles, write headings, and format lists in Telerik UI for .NET MAUI documentation. Preserve the purpose of each article type and the repository's navigation conventions.

## Article Structure

Every documentation article follows a predictable structure that helps readers scan and find information quickly.

### Standard Article Skeleton

```markdown
---
title: Getting Started
page_title: .NET MAUI DataGrid Documentation - Getting Started
slug: datagrid-getting-started
description: "Learn how to add the Telerik UI for .NET MAUI DataGrid to your app, configure the required setup, and display a collection of items."
components: ["datagrid"]
tags: .net maui, datagrid, getting started
position: 1
---

# Getting Started with the .NET MAUI DataGrid

Brief introduction explaining the control and the result the reader will achieve.

## Prerequisites

State the supported .NET and Telerik versions, target platform, package, licensing, and app setup. Link to the shared setup guide rather than duplicating version matrices.

## Define the Control

Show the XAML namespace and control markup. Explain the required registration in MauiProgram.cs, or link to the completed setup step.

## Bind Sample Data

Provide models, sample data, binding context or ItemsSource assignment, and the expected result. Identify the filename and insertion point of each fragment.

## Additional Resources

Link to the same control's data binding, commands, styling, or other next-step articles.

## See Also

* [DataGrid Overview]({%slug datagrid-overview%})
* [System Requirements]({%slug system-requirements%})
```

This skeleton illustrates a control getting-started page, not a requirement to add every section to every article. See the [actual DataGrid guide](../../../../controls/datagrid/getting-started.md) and the [metadata skill](../style-metadata-links/SKILL.md) for field and link conventions.

### MAUI Article Types

Choose the structure that matches the reader's task:

| Article Type | Content and Validation Focus |
|---|---|
| Getting Started | Prerequisites, package and licensing setup, `UseTelerik()`, XAML namespace, minimal control, sample data, and observable result |
| Installation | Supported SDK/workloads and tools, NuGet setup, license activation, platform prerequisites, and verification; never embed credentials |
| Fundamentals | XAML/C#, MVVM, binding contexts, notifications, commands, behaviors, triggers, resource dictionaries, Shell Navigation, and dependency injection as relevant |
| Control Overview | Purpose, supported features, control identity, platform limitations, and links to Getting Started and feature pages |
| Data Binding | Data model, `ItemsSource`, `BindingContext`, binding paths, item contexts, notifications, and compiled binding types where used |
| Commands | Exact command API, execution conditions, parameters, `CanExecute` where applicable, and MVVM setup |
| Styling | Supported setters, target types, resources, themes, contrast, and text scaling |
| Templating | Template property, `DataTemplate` or `ControlTemplate` contract, binding context, and preserved interaction/accessibility |
| Events | Exact event name, signature, event arguments, subscription context, and lifetime/unsubscription where relevant |
| Localization | Localization resources, culture-sensitive formatting, right-to-left support, and control/platform scope |
| Accessibility | Accessible names and semantics, screen-reader behavior, focus order, keyboard support by platform, contrast, scaling, and verification evidence |
| Troubleshooting | Symptoms, environment, evidence, cause when known, scoped fix or workaround, limitations, and verification |
| KB Articles | Environment, Description, Cause for troubleshooting, Solution, and related links; follow the [KB skill](../style-kb-faq/SKILL.md) |

These are authoring scenarios, not a mandate to create new folders or taxonomy values. Reuse shared templates for platform requirements and setup. Do not copy volatile compatibility tables into feature articles.

### Structural Rules

1. **One rendered H1 per documentation article** — Control articles have one descriptive source H1, such as "Getting Started with the .NET MAUI DataGrid", while `title` can remain "Getting Started" for navigation. KB templates must generate the title without a source H1. Inspect the article type and rendering convention before adding or removing a heading; never create a duplicate rendered H1 or force short navigation labels into descriptive headings.
2. **Text between heading and subheadings** — Always write at least one sentence between a heading and its first subheading. This gives readers context before they dive into subsections.
3. **Minimum two subheadings** — If a section has subheadings, it must have at least two. A single subheading under a heading is a sign the content should be merged with the parent.
4. **Heading levels do not skip** — Go from H2 to H3, not from H2 to H4. Every heading level must be one deeper than its parent.
5. **"See Also" section** — Place a "See Also" section at the end of the article with links to related content. This is a convention, not a hard requirement.

## Title Case Capitalization

All headings use **title case**. Title case capitalizes most words but keeps certain short words lowercase.

### Capitalize These Words

- **Nouns**: Document, Page, Stream, Table, Field
- **Verbs** (including short ones): Is, Are, Was, Be, Do, Has, Get, Set, Run, Use
- **Adjectives**: Fixed, Custom, New, Digital, Large
- **Adverbs**: Always, Never, Quickly, Also
- **Pronouns**: You, Your, It, Its, They, Their
- **Subordinating conjunctions**: If, When, Because, Although, While, Since, After, Before, Until

### Keep These Words Lowercase

(unless they are the first or last word of the heading)

- **Articles**: a, an, the
- **Coordinating conjunctions**: and, but, or, nor, for, yet, so
- **Short prepositions** (4 letters or fewer): in, on, at, to, by, for, of, up, off, out, with
- **"to" in infinitives**: How to Export, Getting to Know

### First and Last Words

Always capitalize the **first word** and the **last word** of a heading, regardless of the rules above.

### Examples

| ❌ Wrong | ✅ Correct |
|---|---|
| How to bind data to the datagrid | How to Bind Data to the DataGrid |
| Working with collectionview templates | Working with CollectionView Templates |
| Getting started with the api | Getting Started with the API |
| Create And Style a treeview | Create and Style a TreeView |
| Loading data From A remote Source | Loading Data from a Remote Source |

### Tricky Cases

| Word | Rule | Example |
|------|------|---------|
| is, are, was, be | Verb — capitalize | "What Is a Binding Context" |
| it, its | Pronoun — capitalize | "How It Works" |
| with | Preposition (4 letters) — lowercase | "Working with Commands" |
| from | Preposition (4 letters) — lowercase | "Import Data from a File" |
| into | Preposition (4 letters) — lowercase | "Load Data into a CollectionView" |
| through | Preposition (7 letters) — capitalize | "Iterating Through Items" |
| between | Preposition (7 letters) — capitalize | "Navigating Between Pages" |

## Heading Style

### -ing Forms in Headings

**-ing forms (gerunds) are acceptable and often preferred in task-oriented headings.** Body text favors direct verbs, but established terms such as data binding and templating remain unchanged.

```markdown
## Configuring the DataGrid Columns   ✅ (heading — gerund OK)
## Loading Data from a Remote Source   ✅ (heading — gerund OK)
## How to Configure DataGrid Columns  ✅ (alternative form)
```

### Parallel Headings

Headings at the same level within a section should follow the same grammatical pattern.

| ❌ Inconsistent | ✅ Parallel |
|---|---|
| ## Installing the Package / ## Configuration / ## How to Run Tests | ## Installing the Package / ## Configuring the Settings / ## Running the Tests |
| ## Bind Data / ## Styling / ## The Template | ## Binding Data / ## Styling the Control / ## Templating Items |

### Heading Content Rules

- **No inline code in headings** — Avoid backtick-formatted code in headings when possible. Use plain text or rephrase.
   - ❌ `## Using the \`ItemsSource\` Property`
   - ✅ `## Setting the Items Source`
- **No links in headings** — Do not place hyperlinks inside heading text.
- **No trailing punctuation** — Do not end headings with periods, colons, or question marks (except FAQ headings, which use question marks by design).

## Lists

Lists make information scannable. Use them for sequences of steps, sets of options, or collections of related items.

### Ordered Lists (Numbered)

Use ordered lists for **sequential steps** where order matters:

```markdown
1. Install the documented Telerik UI for .NET MAUI package.
2. Register the Telerik controls in MauiProgram.cs.
3. Add the DataGrid to the XAML page.
4. Assign the sample collection to ItemsSource.
```

### Unordered Lists (Bulleted)

Use unordered lists for **non-sequential items** where order does not matter:

```markdown
The suite includes the following controls:

* DataGrid
* CollectionView
* TreeView
* Scheduler
```

### List Formatting Rules

1. **Introductory sentence** — Always precede a list with an introductory sentence that ends with a **colon** (`:`).

2. **Capitalize the first word** — Every list item starts with a capital letter.

3. **Punctuation consistency** — If any list item is a complete sentence, **all items** in that list must be complete sentences and end with a period. If all items are fragments, none end with a period.

   ```markdown
   ✅ All fragments (no periods):
   * Data binding
   * Item selection
   * Item templating

   ✅ All complete sentences (all periods):
   * The CollectionView displays bound items.
   * The TreeView displays hierarchical data.
   * The Scheduler displays appointments.

   ❌ Mixed (some periods, some not):
   * The CollectionView displays bound items.
   * Item selection
   * The Scheduler displays appointments.
   ```

4. **Parallel structure** — All items in a list should follow the same grammatical pattern.

   ```markdown
   ❌ Not parallel:
   * Bind the data.
   * Configuration of settings.
   * You can import data.

   ✅ Parallel:
   * Bind the data.
   * Configure the settings.
   * Import the data.
   ```

5. **No single-item lists** — A list with one item is not a list. Convert it to a regular sentence.

6. **Nesting depth** — Do not nest lists more than **three levels** deep. If you need more depth, restructure the content into subsections.

7. **List marker consistency** — Use `*` for unordered lists (not `-` or `+`). Use `1.`, `2.`, `3.` for ordered lists.

## Figures and Captions

When inserting figures (images, diagrams, charts):

1. Introduce the figure in the preceding text.
2. Use descriptive alt text in the image tag.
3. If the figure needs additional explanation, add a caption as italic text immediately after the image.

```markdown
For a DataGrid article, introduce the existing control screenshot:

![DataGrid displaying countries and capitals](images/datagrid-getting-started.png)

*Figure 1: The DataGrid displays the sample collection.*
```

## Quick Checklist

When reviewing an article for structure, verify:

- [ ] Exactly one rendered H1; descriptive control headings and generated KB titles follow their own conventions
- [ ] Article structure matches its MAUI task rather than an unrelated product workflow
- [ ] Setup, XAML/C# context, sample data, expected result, platform scope, and version prerequisites are present where relevant
- [ ] Accessibility and localization articles identify supported platforms and evidence, not assumed parity
- [ ] Text between every heading and its first subheading
- [ ] At least two subheadings per section (or none)
- [ ] Heading levels do not skip (H2→H3, never H2→H4)
- [ ] All headings use title case capitalization
- [ ] Headings at the same level use parallel structure
- [ ] No inline code, links, or trailing punctuation in headings, except question marks in FAQ headings
- [ ] Every list has an introductory sentence ending with a colon
- [ ] List items are capitalized and have consistent punctuation
- [ ] List items use parallel grammatical structure
- [ ] No single-item lists
- [ ] Lists nested no deeper than three levels
- [ ] Related links stay within the intended control family and navigation path
