---
name: style-formatting
description: "Use this skill when formatting Telerik UI for .NET MAUI documentation: UI labels, API references, keyboard shortcuts, paths, menus, admonitions, XAML and C# examples, external snippets, screenshots, and command-line instructions. Covers code context, MAUI namespaces, accessible visuals, and platform-specific captures. Use when asked to 'format the article', 'fix formatting', 'add a note', 'add a screenshot', or 'check code blocks'."
---

# Element Formatting, Admonitions, and Visual Content

This skill defines how to format inline elements, admonitions (notes, tips, cautions), code blocks, screenshots, and command-line instructions in Telerik UI for .NET MAUI documentation. Preserve the repository's rendering syntax and each sample's technical meaning.

## Why Consistent Formatting Matters

Consistent formatting acts as a visual language — readers learn to recognize bold as a UI element, monospace as code, and italic as a new term. Breaking these conventions forces readers to re-evaluate what each piece of text means.

## Inline Element Formatting

### UI Elements — Bold

Format all **user interface element names** in bold. This includes button labels, menu names, dialog box titles, tab names, checkbox labels, field names, and window titles.

```markdown
Select **Add** in the sample app to add an item to the CollectionView.
In Visual Studio, select **Project** > **Manage NuGet Packages**.
In the sample app, clear the **Show Details** checkbox.
```

**Bold syntax**: Always use asterisks to format bold text (`**bold text**`). Do not use the underscore syntax (`__bold text__`), which renders identically but reduces source readability and is inconsistent with the rest of the codebase.

| ❌ Wrong | ✅ Correct |
|---|---|
| `__Add__` | `**Add**` |
| `__Manage NuGet Packages__` | `**Manage NuGet Packages**` |

### Code References — Monospace

Format code elements in `monospace` (backticks). This includes **any mention of an API type, method, property, or member**, as well as enum values, parameters, file names, file extensions, XML/HTML tags, API endpoints, namespaces, and inline code expressions. Every API reference — no matter how brief — must appear in monospace.

```markdown
Call `UseTelerik()` in `MauiProgram.cs` to register the Telerik controls.
Set the `ItemsSource` property to your collection.
The `RadDataGrid` class displays tabular data.
Open the `MainPage.xaml` file.
Set the page's `BindingContext` before evaluating its bindings.
```

| ❌ Wrong | ✅ Correct |
|---|---|
| The RadDataGrid control displays items. | The `RadDataGrid` control displays items. |
| Call UseTelerik() to register the controls. | Call `UseTelerik()` to register the controls. |
| Set BindingContext to the viewmodel. | Set `BindingContext` to the viewmodel. |

### New Terms — Italic

Format a term in *italic* on its first occurrence in an article when introducing it as a concept. Do not italicize the term on subsequent occurrences.

```markdown
A *binding context* supplies the source object for bindings on a view.
An item template typically uses the item as its binding context.
```

### Keyboard Keys — Monospace

Format individual keyboard keys in monospace. Use `+` to combine keys in a keyboard shortcut. Do not add spaces around `+`.

```markdown
Press `Enter` to confirm.
Press `Ctrl`+`S` to save the XAML file in Visual Studio on Windows.
Press `Ctrl`+`Shift`+`P` to open the command palette.
```

### File Paths — Monospace

Format file paths in monospace:

```markdown
Open `MauiProgram.cs` in the app project.
Android-specific configuration belongs under `Platforms/Android/`.
```

### Menu Sequences — Bold with Angle Brackets

Format menu navigation sequences with bold for each element and `>` as separator:

```markdown
In Visual Studio on Windows, select **Project** > **Manage NuGet Packages**.
In the SDKBrowser app, select **CollectionView** > **Getting Started**.
```

### Parameter Names in Instructions

When documenting command-line tools, use **bold** for literal parts (type exactly as shown) and *italic* for placeholders (user-supplied values):

```markdown
**dotnet** **add** **package** *package-name* **--version** *version-number*
```

For a command the reader can run, use a fenced shell block. Identify the working directory and replaceable values in the surrounding text. Never include a real license key or NuGet feed credential.

## Admonitions (Notes, Tips, Cautions)

Admonitions highlight important information that stands apart from the main text. Use the blockquote-based syntax specific to this documentation platform.

### Note

Use for supplementary information the reader should be aware of:

```markdown
> A note provides additional context that may be useful but is not critical to the task.
```

The repository also uses `>note` for explicitly labeled notes. Use the existing article's supported form; do not introduce GitHub alert syntax.

### Tip

Use for helpful suggestions that improve the reader's experience:

```markdown
>tip A tip provides a useful suggestion or shortcut.
```

Use the site's tip rendering rather than a custom HTML callout.

### Important / Caution

Use for warnings about potential issues, data loss, or breaking changes:

```markdown
>important An important note warns about potential issues or required prerequisites.
```

Use `>caution` or `>warning` only where supported by the documentation renderer and appropriate to the risk. Do not promise a particular label color or use color alone to communicate severity.

### Admonition Rules

- Place admonitions **after** the paragraph they relate to, not before.
- Do not stack multiple admonitions consecutively — separate them with regular text.
- Keep admonition text concise — one to three sentences.
- Do not use admonitions for routine information that belongs in the main text.
- A note that applies to every reader is probably not a note — it is main content.

## Code Blocks

### Fenced Code Blocks with Language

Always specify the language identifier after the opening triple backticks. MAUI articles use `XAML` for markup and `C#` for application code; retain supported aliases such as `xml` and `csharp` when already used:

````markdown
```XAML
<telerik:RadDataGrid x:Name="dataGrid" />
```
````

Common language identifiers: `XAML`, `C#`, `csharp`, `xml`, `json`, `powershell`, `bash`. Use other languages only when the MAUI scenario actually requires them.

### Code Block Rules

1. **Complete examples or explicit fragments** — State the filename, prerequisites, and insertion point. A full sample needs matching XAML and C# classes, models, data, resources, and handlers. Label partial examples as fragments.
2. **No line numbers in markdown** — The rendering engine adds line numbers if needed.
3. **No trailing whitespace** — Remove trailing spaces from code lines.
4. **Consistent indentation** — Use 4 spaces for new C# examples and consistent indentation for XAML/XML/JSON. Preserve the indentation of shared source snippets.
5. **Meaningful variable names** — Use descriptive names, not single letters (except loop counters).

### MAUI Sample Context

For a page example, establish the app setup first: install the documented package, configure licensing, and call `UseTelerik()` with the imports shown in the [DataGrid setup guide](../../../../controls/datagrid/getting-started.md). The following `MainPage.xaml` and `MainPage.xaml.cs` pair assumes that setup and an app namespace of `MauiDocs`:

```XAML
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
			 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
			 xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
			 x:Class="MauiDocs.MainPage">
  <Grid>
	<telerik:RadDataGrid x:Name="dataGrid" />
  </Grid>
</ContentPage>
```

```csharp
using System.Collections.Generic;
using Microsoft.Maui.Controls;

namespace MauiDocs;

public partial class MainPage : ContentPage
{
	public MainPage()
	{
		InitializeComponent();
		dataGrid.ItemsSource = new List<City>
		{
			new City { Country = "India", Capital = "New Delhi" },
			new City { Country = "Singapore", Capital = "Singapore" }
		};
	}
}

public class City
{
	public string Country { get; set; } = string.Empty;
	public string Capital { get; set; } = string.Empty;
}
```

Validate XAML as XML and against the actual control APIs. Check namespace declarations, `x:Class`, named elements, resource keys, and supported properties. XML parsing alone cannot prove XAML compilation or binding correctness. For MVVM examples, also verify `BindingContext`, item contexts, notifications, `ICommand` parameters, and any toolkit or DI registration.

### Shared Snippet References

Keep external snippet placeholders intact unless the source change is part of the task. The [build configuration](../../../../docs-builder.yml) sets `external-snippets-path: ../maui`; resolve IDs against the configured MAUI source checkout. For example, the [CollectionView guide](../../../../controls/collectionview/getting-started.md) uses:

```xml
<snippet id='collectionview-gettingstarted-xaml'/>
<snippet id='collectionview-getting-started-csharp'/>
```

Verify the referenced code, not just the placeholder. If the source checkout is unavailable, state that limitation; do not invent snippet IDs or claim compilation. When showing markdown that contains fenced code, use a longer outer fence so the inner code remains inside the example.

### Code Comments in Examples

When code examples include comments:

- Write comments in **English**.
- Keep comments to **80 characters or fewer** per line.
- Use full sentences starting with a capital letter and ending with a period.
- Comment only what is not obvious from the code itself.

Do not add comments that narrate assignments or control creation. Explain setup and platform restrictions in the surrounding prose; preserve useful comments in resolved source snippets.

## Screenshots

Screenshots complement text but do not replace it. Always describe the action or result in text before or after the screenshot.

### Screenshot Requirements

| Rule | Specification |
|------|--------------|
| Appearance | Default control theme and font size unless styling, dark theme, or text scaling is the subject; identify any deliberate variation |
| Background | White or the application's default background |
| Size | Maximum 1000 pixels wide |
| Format | PNG for UI screenshots, SVG for diagrams |
| Annotations | Arrows to point, boxes to surround areas of interest |
| Annotation style | Arial 16pt, primary color `#f56147` (Telerik red-orange) |
| Cropping | Show the relevant control and enough context; remove IDE, emulator, or OS chrome unless relevant |
| Personal data | Remove or redact any personal information, real email addresses, or real user names |
| Platform | Identify Android, iOS, Mac Catalyst, or Windows; do not present one capture as proof of platform parity |
| Accessibility | Provide a text equivalent; do not rely on color, annotation position, or a screenshot as proof of screen-reader support |

### Screenshot Placement

For an article in `controls/datagrid/`, use the existing getting-started asset:

```markdown
The DataGrid displays countries and capitals from the sample collection.

![DataGrid displaying countries and capitals](images/datagrid-getting-started.png)
```

- Place screenshots **after** the text that describes them.
- Use descriptive alt text that explains what the screenshot shows.
- Store screenshot files in an `images/` subdirectory relative to the article.

## Tables

### When to Use Tables

Use tables for structured data with two or more columns and three or more rows. Do not use tables for simple lists or single-column data.

### Table Formatting

- Include a header row with descriptive column names.
- Align content to the left (default).
- Keep cell content concise — avoid long paragraphs in table cells.
- Introduce every table with a sentence ending in a colon or period.

```markdown
The following table distinguishes common data controls:

| Control | API Type | Data Shape |
|--------|-----------|-------------|
| DataGrid | `RadDataGrid` | Tabular items |
| CollectionView | `RadCollectionView` | Item collections |
| TreeView | `RadTreeView` | Hierarchical items |
```

## Quick Checklist

When reviewing an article for formatting, verify:

- [ ] UI elements (buttons, menus, tabs, fields) are in **bold**
- [ ] Bold uses `**` asterisk syntax, not `__` underscore syntax
- [ ] All API mentions (types, methods, properties, members) are in `monospace`
- [ ] Code elements (methods, classes, properties, file names) are in `monospace`
- [ ] New terms are in *italic* on first occurrence only
- [ ] Keyboard shortcuts use `Key`+`Key` format in monospace
- [ ] Menu sequences use **Menu** > **Item** format
- [ ] Notes use `>` syntax, tips use `>tip`, important items use `>important`, cautions use `>caution`, and warnings use `>warning`
- [ ] Admonitions follow related text, are concise, and are not stacked
- [ ] Code blocks specify the language identifier
- [ ] XAML namespaces, class names, resources, bindings, and control APIs match the target release
- [ ] C# examples include the required types, imports, setup, and event or command contracts
- [ ] External snippet IDs resolve to reviewed source; missing source or untested compilation is disclosed
- [ ] Nested markdown examples use longer outer fences
- [ ] Code comments are English, ≤80 chars, full sentences
- [ ] Screenshots have descriptive alt text and are ≤1000px wide
- [ ] Captures identify their platform and explain theme or scaling variations
- [ ] Text covers the workflow and accessibility details independently of screenshots and color
- [ ] Tables have header rows and introductory text
