---
name: style-kb-faq
description: "Use this skill when writing, editing, or reviewing Telerik UI for .NET MAUI Knowledge Base articles and FAQs. Covers how-to, troubleshooting, approved security advisories, environment and platform evidence, XAML/C# samples, binding and layout diagnosis, customer-data sanitization, and concise answers. Use when asked to 'write a KB article', 'create a troubleshooting guide', 'add FAQ questions', 'write a how-to', or 'document a workaround'."
---

# Knowledge Base and FAQ Articles

This skill defines how to write Knowledge Base (KB) articles and FAQ sections in Telerik UI for .NET MAUI documentation. KB articles address specific control or application problems; FAQs answer common questions concisely. Use the [metadata skill](../style-metadata-links/SKILL.md) for taxonomy, links, and authorized frontmatter edits.

## KB Article Types

There are three types of KB articles, each with a distinct purpose and structure.

KB articles must contain no H1. Flag any H1 and, when editing is authorized, remove a redundant title or convert a meaningful heading at the appropriate level while preserving hierarchy. Never add an H1 to KB content.

### 1. How-To Articles

How-to articles guide the reader through accomplishing a specific task.

**Title format**: Use an **-ing form** (gerund) that describes the task:
- ✅ "Binding a CollectionView to Observable Data"
- ✅ "Styling DataGrid Column Headers"
- ❌ "How to Bind a CollectionView" (avoid "How to" in the title)
- ❌ "Bind Data" (too terse; use -ing form)

**Required sections**: The following template uses metadata for the title, as in existing MAUI KB pages. KB source must never contain an H1, even if a template does not generate a title. Replace every environment placeholder with tested values before publishing.

````markdown
---
title: Binding a CollectionView to Observable Data
description: "Bind the Telerik UI for .NET MAUI CollectionView to observable data, set the page binding context, and display updates in your app."
type: how-to
res_type: kb
page_title: Bind CollectionView to Observable Data - .NET MAUI Knowledge Base
slug: kb-collectionview-observable-data
components: ["collectionview"]
tags: .net maui, collectionview, data binding, observablecollection
---

## Environment

| Property | Value |
|----------|-------|
| Product | Progress® Telerik® UI for .NET MAUI |
| Control | CollectionView |
| Telerik Version | `TESTED_PACKAGE_VERSION` |
| .NET SDK | `TESTED_SDK_VERSION` |
| Target Framework | `TESTED_PLATFORM_TFM` |
| Platform | `TESTED_OS_VERSION_AND_DEVICE` |

## Description

Display a collection in a Telerik CollectionView and notify the control when items are added or removed.

## Solution

Start with a configured MAUI app using the [CollectionView setup guide]({%slug collectionview-getting-started%}). The fragments below assume a page with the Telerik XAML namespace declared and controls registered through `UseTelerik()`.

1. Add the data model and viewmodel to the app namespace:

```csharp
using System.Collections.ObjectModel;

public class City
{
      public string Name { get; set; } = string.Empty;
}

public class CitiesViewModel
{
      public ObservableCollection<City> Cities { get; } = new()
      {
            new City { Name = "Sofia" },
            new City { Name = "Tokyo" }
      };
}
```

2. Add this XAML fragment inside the page's bounded layout:

```XAML
<telerik:RadCollectionView ItemsSource="{Binding Cities}">
   <telerik:RadCollectionView.ItemTemplate>
      <DataTemplate>
         <Label Text="{Binding Name}" />
      </DataTemplate>
   </telerik:RadCollectionView.ItemTemplate>
</telerik:RadCollectionView>
```

3. Assign the page's binding context after `InitializeComponent()` in its constructor:

```csharp
BindingContext = new CitiesViewModel();
```

Run the app on the recorded target platform. Confirm that the CollectionView displays Sofia and Tokyo. Add an item to `Cities` on the UI thread and confirm that it appears.

## Notes

`ObservableCollection<T>` notifies collection changes. Changes to an existing city's `Name` need `INotifyPropertyChanged` or an equivalent notification mechanism; the model above does not implement it. If the page uses compiled bindings, set the correct `x:DataType` for the page and the item template.

## See Also

* [CollectionView Data Binding]({%slug collectionview-data-binding%})
* [CollectionView Commands]({%slug collectionview-commands%})
````

### 2. Troubleshooting Articles

Troubleshooting articles help readers diagnose and fix a specific problem.

**Title format**: Use a **sentence that states the problem**:
- ✅ "DataGrid Does Not Display Items in an Unbounded Layout"
- ✅ "CollectionView Does Not Reflect Item Property Changes"
- ❌ "Fixing DataGrid Issues" (too vague; state the specific problem)
- ❌ "Binding Error" (too terse; describe the context)

**Required sections**:

````markdown
---
title: DataGrid Does Not Display Items in an Unbounded Layout
description: "Resolve a Telerik UI for .NET MAUI DataGrid layout issue by giving the control bounded space and checking its sample data and parent layout."
type: troubleshooting
res_type: kb
page_title: Resolve DataGrid Unbounded Layout - .NET MAUI Knowledge Base
slug: kb-datagrid-unbounded-layout
components: ["datagrid"]
tags: .net maui, datagrid, layout, virtualization, troubleshooting
---

## Environment

| Property | Value |
|----------|-------|
| Product | Progress® Telerik® UI for .NET MAUI |
| Control | DataGrid |
| Telerik Version | `TESTED_PACKAGE_VERSION` |
| .NET SDK | `TESTED_SDK_VERSION` |
| Target Framework | `TESTED_PLATFORM_TFM` |
| Platform | `TESTED_OS_VERSION_AND_DEVICE` |

## Description

The DataGrid does not display its items correctly when its parent measures it with infinite height. This scenario places the DataGrid inside a `ScrollView`. Record the observed behavior and exact layout from the reproduction.

## Cause

The DataGrid uses UI virtualization and requires bounded space. A `ScrollView` parent can measure its content without a finite height. Confirm this cause by reproducing the issue with the same data in a bounded layout.

## Solution

In a configured DataGrid page, remove the outer `ScrollView` and put the control in a `Grid` with an available, bounded size. Use this fragment as the page content, and keep the page itself in a bounded host:

```XAML
<Grid RowDefinitions="*">
   <telerik:RadDataGrid x:Name="dataGrid" />
</Grid>
```

To isolate the layout from binding problems, assign this sample collection after `InitializeComponent()` in the page constructor:

```csharp
dataGrid.ItemsSource = new[]
{
      new { Country = "India", Capital = "New Delhi" },
      new { Country = "Singapore", Capital = "Singapore" }
};
```

Run the app on the recorded platform and confirm that both items appear. Reconnect the original binding and verify scrolling with representative data. If the issue remains, inspect `BindingContext`, `ItemsSource`, binding diagnostics, and parent constraints instead of assuming every empty grid has the same cause.

## Notes

State tested limitations and distinguish a workaround from a product fix. Do not promise that this layout resolves unrelated binding, data, or platform issues.

## See Also

* [DataGrid Setup and Layout Requirements]({%slug datagrid-getting-started%})
````

### 3. CVE / Security Articles

CVE articles document security vulnerabilities and their fixes. These follow a template provided by the security team. Key rules:

- Use the exact CVE identifier in the title.
- Include the severity rating and affected versions.
- Describe the vulnerability and its impact without providing exploit details.
- Link to the fix version and upgrade instructions.
- Do not speculate about attack vectors beyond what the CVE officially describes.
- Confirm that the advisory actually affects Telerik UI for .NET MAUI or an included dependency. Use the approved advisory's affected/fixed versions and mitigation; do not infer a vulnerability from an exception or reuse another product's advisory.

## KB Content Quality Rules

### Self-Sufficient Articles

Every KB article must be **self-sufficient for its stated task**. Name foundational prerequisites and link to shared installation, licensing, or Getting Started guidance rather than duplicating it. Once those prerequisites are met, provide the code, insertion points, data, and verification needed for the fix; do not hide the solution behind another article or support ticket.

### Technical Accuracy

- Complete samples must compile and run; label fragments and identify their containing page, class, imports, and setup. Follow [style-formatting](../style-formatting/SKILL.md) for code and external snippet validation.
- All file paths, class names, method names, and parameter names must be accurate.
- Record the tested Telerik package, .NET SDK/target framework, target OS, and relevant workload or native toolchain. Consult system requirements instead of assuming the newest version is compatible.
- Record the full SDK version separately from the platform-specific target framework moniker (TFM). In multi-target apps, list the combinations actually tested. A .NET release label is not an exact SDK version or a platform-specific TFM.
- Validate XAML namespaces and properties, binding contexts, template contexts, C# types, notifications, and command/event contracts against the specific control APIs.
- Test reproduction and solution steps on every claimed platform. If execution is unavailable, state what remains unverified and do not mark the article ready to publish.
- For interaction changes, verify accessible names, focus order, supported keyboard paths, screen-reader behavior, text scaling, and contrast. Do not claim accessibility compliance from code inspection alone.
- Use the control's accessibility documentation to identify prerequisites and platform-specific checks. For example, CollectionView documents [screen readers](../../../../controls/collectionview/accessibility/screen-reader.md) and [Windows keyboard navigation](../../../../controls/collectionview/accessibility/keyboard-navigation/windows.md). Verify announcements with TalkBack on Android, VoiceOver on Apple platforms, or Narrator on Windows as applicable; do not transfer one control's automation settings to another.
- Distinguish documented support from observed test results. State which combinations pass, fail, have a known limitation, or remain untested; an untested platform is not automatically unsupported.
- Distinguish Debug from Release and check trimming, AOT, permissions, assets, and lifecycle behavior only where relevant to the problem. Request sanitized diagnostics, not entire customer projects.

### Short, Simple, Clear

- Write short sentences (25 words or fewer).
- Use simple vocabulary (see the `style-grammar-words` skill).
- Maintain a clear, direct tone (see the `style-writing-tone` skill).
- Get to the solution quickly — readers arrive at KB articles with a problem to solve.

### Working Links

- All internal links must use the `{%slug ...%}` syntax.
- Check external destinations for relevance and availability. Follow site-renderer behavior; do not require a new tab. Disclose unavailable link checks.
- No orphaned links — every link must point to a live, relevant destination.

### No Sensitive Information

- Do not include real customer names, email addresses, or company names.
- Redact or replace any personal information in code examples or screenshots.
- Use generic placeholder data: "john.doe@example.com", "Contoso Ltd.", "user123".

## Balancing Customer Context

KB articles often originate from customer support interactions. When converting a support case into a KB article:

1. **Generalize the problem** — Remove customer-specific details. Describe the problem in universal terms.
2. **Keep the scenario realistic** — While generalizing, preserve enough context so readers can recognize their own situation.
3. **Correct grammar and style** — Customer-submitted text may have errors. Fix grammar but preserve the technical meaning.
4. **Verify the solution** — Customer-provided workarounds may be suboptimal. Test and refine the solution before publishing.

| ❌ Too customer-specific | ✅ Generalized |
|---|---|
| John from Acme Corp reported that their CollectionView does not update the customer name after an edit. | The CollectionView does not reflect item-property changes when the item model does not raise property-change notifications. |
| A customer's Windows DataGrid is empty inside their custom scrolling layout. | In the reproduced Windows layout, a ScrollView measures the DataGrid without bounded height. Verify the cause before applying the layout fix to other platforms. |

## FAQ Sections

FAQ sections answer common questions concisely within a feature article or as standalone FAQ pages.

### FAQ Formatting Rules

Apply the containing article's H1 rule before formatting questions: a standard standalone FAQ needs exactly one H1, while a KB FAQ must have none. The examples below are section fragments, not complete standard articles.

1. **Headings as questions** — Each FAQ item uses a heading formatted as a complete question with a question mark.

   ```markdown
   ## How Do I Supply Data to the DataGrid?

   Set the DataGrid's `ItemsSource` to a collection of items.

   ## Does ObservableCollection Update Item Properties?

   No. It notifies collection changes; item-property changes need their own notifications.
   ```

2. **Title case for question headings** — Apply the same title case rules as all other headings (see the `style-structure` skill).

3. **Self-sufficient answers** — Each answer must stand alone. Do not refer to other FAQ items with "see above" or "as mentioned earlier."

4. **Concise answers** — Keep answers to 1–4 sentences. If the answer needs more detail, write a full article and link to it.

5. **Link to detailed articles** — When a full explanation exists elsewhere, give a brief answer and link to the detailed article.

   ```markdown
   ## How Do I Add a CollectionView to a Page?

   Configure the Telerik package and control registration, then declare a `RadCollectionView` in XAML.
   See the [CollectionView setup guide]({%slug collectionview-getting-started%}) for the complete example.
   ```

## Quick Checklist

When reviewing a KB or FAQ article, verify:

- [ ] KB articles, including KB FAQs, contain no H1; existing H1s are flagged for removal/conversion and no fix adds one
- [ ] Standard articles, including standalone non-KB FAQs, have exactly one H1; missing/multiple H1s are flagged and hierarchy is preserved
- [ ] Article type matches the content (how-to, troubleshooting, or CVE)
- [ ] Title uses the correct format (-ing form for how-to, problem statement for troubleshooting)
- [ ] Environment, Description, and Solution are present; troubleshooting adds Cause when confirmed
- [ ] Tested Telerik/.NET versions, platform, device, and relevant tools are recorded without unsupported version ranges
- [ ] Article includes the entire task or fix after explicitly named foundational prerequisites
- [ ] XAML and C# examples match the control API, compile in their documented context, and have a verified expected result
- [ ] Binding, commands, layout, accessibility, and cross-platform behavior are checked where relevant
- [ ] Supported, limited, failing, and untested platform combinations are distinguished with evidence
- [ ] `type`, `res_type: kb`, control taxonomy, and generated-title conventions match repository practices
- [ ] Workarounds, fixed versions, security claims, and untested behavior are clearly distinguished
- [ ] No sensitive customer information
- [ ] All links work and use correct syntax
- [ ] FAQ headings are questions with question marks
- [ ] FAQ answers are concise and self-sufficient
- [ ] Description metadata is between 120 and 150 characters and unique
