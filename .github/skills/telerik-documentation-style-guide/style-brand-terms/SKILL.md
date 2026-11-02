---
name: style-brand-terms
description: "Use this skill to write or review Telerik UI for .NET MAUI brand names, trademarks, interaction verbs (click/tap/select/press), and technical vocabulary. Covers controls, XAML, C#, MVVM, data binding, commands, behaviors, triggers, resource dictionaries, navigation, platform support, Document Processing, and licensing. Use when asked to 'fix brand names', 'check product references', 'review interaction verbs', or 'correct terminology' in MAUI documentation."
---

# Telerik UI for .NET MAUI Brand Names, Interaction Verbs, and Vocabulary

This skill defines how to write brand names, describe user interactions, and use standard vocabulary in Telerik UI for .NET MAUI documentation. Preserve the article's task and technical behavior while correcting terminology.

Use this skill for customer documentation and support guidance about native cross-platform controls and the included Document Processing libraries. Distinguish Telerik controls from Microsoft .NET MAUI controls and application-owned services. This is a terminology review, not a substitute for API validation, platform testing, or a security assessment.

## Brand Names and Trademarks

Apply these rules to prose examples and customer-facing instructions. Preserve exact API identifiers, package names, configuration keys, error messages, and UI labels.

### First Use in an Article

On the **first mention in article body prose**, use the full brand name with the trademark symbol. Do not insert trademark symbols into headings, SEO metadata, code, package names, or exact UI labels:

```markdown
Progress® Telerik® UI for .NET MAUI provides controls for native mobile and desktop applications.
```

### Subsequent Uses

After the first mention, use only the product name without the trademark symbol:

```markdown
Telerik UI for .NET MAUI provides DataGrid, CollectionView, and Scheduler controls.
```

Or use the shorter, commonly recognized name if the full name is unwieldy:

```markdown
The DataGrid displays the collection assigned to its `ItemsSource` property.
```

### Trademark Rules

1. **Never pluralize a trademark** — Trademarks are proper nouns and cannot be made plural.
   - ❌ "Telerik UIs for .NET MAUI"
   - ✅ "Telerik UI for .NET MAUI controls"

2. **Never use a trademark as a verb** — Trademarks are nouns or adjectives.
   - ❌ "Telerik the app"
   - ✅ "Build the app with Telerik UI for .NET MAUI"

3. **Never form possessives with trademarks** — Do not add 's to brand names.
   - ❌ "Telerik UI for .NET MAUI's API"
   - ✅ "The Telerik UI for .NET MAUI API"

4. **Lowercase generic nouns after product names** — The product name is the proper noun; the generic category noun that follows is lowercase.
   - ❌ "`RadDataGrid` Class"
   - ✅ "`RadDataGrid` class"
   - ❌ "`RadCollectionView` Object"
   - ✅ "`RadCollectionView` object"

### Common Product Names

| Full Name (first use) | Subsequent uses |
|---|---|
| Progress® Telerik® UI for .NET MAUI | Telerik UI for .NET MAUI, the suite (when unambiguous) |
| Microsoft .NET MAUI | .NET MAUI, the framework (when unambiguous; no Telerik trademark) |

Use NuGet as the package-manager name, not as a Progress product name. Write exact package identifiers, such as `Telerik.UI.for.Maui`, in monospace and verify them against the [NuGet installation article](../../../../installation/manual-installation-approaches/nuget/overview.md) for the target release.

Use component names consistently: DataGrid, Chart, CollectionView, TreeView, Scheduler, Calendar, RichTextEditor, DataForm, Barcode, NavigationView, and PDF Viewer. Use PdfProcessing for the document library, not the PDF Viewer UI. Preserve the distinction between the Chart and Charts documentation families; do not migrate API identifiers between them. Use the canonical product name in new prose; retain exact legacy labels, package names, slugs, and quoted diagnostics.

## Interaction Verbs

Use the correct verb for how users interact with interface elements. The choice depends on the platform (desktop, mobile, or mixed).

### Desktop Interactions

| Action | Verb | Example |
|--------|------|---------|
| Activate a button or link | **click** | Click **Add** in the sample app. |
| Activate with two rapid clicks | **double-click** | Double-click `MainPage.xaml` in Visual Studio. |
| Activate with the secondary button | **right-click** | Right-click the project in **Solution Explorer**. |
| Activate a keyboard key | **press** | Press `Enter` to confirm. |
| Choose a menu item | **select** | Select **File** > **Save**. |
| Choose from a dropdown | **select** | Select a country in the ComboBox. |
| Mark a checkbox | **select** | Select the **Show Details** checkbox in the sample app. |
| Clear a checkbox | **clear** | Clear the **Show Details** checkbox in the sample app. |
| Enter text in a field | **enter** or **type** | Enter a name in the DataForm editor. |
| Resize a column | **drag** | Drag the DataGrid column boundary when resizing is enabled. |

### Important: "click" Not "click on"

Use **"click"** without "on". The preposition is redundant:

- ❌ Click on the **Save** button.
- ✅ Click the **Save** button.
- ✅ Click **Save**.

### Mobile Interactions

These verbs describe input methods, not guaranteed control capabilities. Verify the control, platform, configuration, and version before documenting a gesture.

| Action | Verb | Example |
|--------|------|---------|
| Activate an element | **tap** | Tap a date in the Calendar. |
| Activate with two rapid taps | **double-tap** | Use only for documented control behavior. |
| Move an element | **drag** | Describe a Scheduler appointment drag only where supported and enabled. |
| Swipe across the screen | **swipe** | Describe a CollectionView swipe action only where configured and supported. |
| Zoom in | **spread** | Use only if the target control supports this zoom gesture. |
| Zoom out | **pinch** | Use only if the target control supports this zoom gesture. |
| Touch and hold | **press and hold** | Use only for a documented touch-and-hold action. |

### Mixed (Desktop + Mobile) Content

When writing for both desktop and mobile, use **"select"** as the universal verb:

```markdown
Select **Add** to add an item to the CollectionView sample.
```

"Select" works across input methods (mouse click, keyboard, touch tap).

## Vocabulary — Standard Terms

Use these standard terms consistently throughout the documentation. Read the [MAUI vocabulary reference](./references/vocabulary.md) for definitions, distinctions, and troubleshooting terminology.

### MAUI Architecture and Scope

Describe the application workflow accurately:

1. Verify the supported .NET SDK, MAUI workload, target platforms, Telerik package version, and license setup.
2. Register Telerik controls with `UseTelerik()` in `MauiProgram.cs` as documented for the release. The linked DataGrid guide imports `Telerik.Maui.Controls.Compatibility` for this extension; do not infer a control type's namespace from that registration import.
3. Declare the control in XAML with `xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` or instantiate its documented C# type.
4. Provide data and behavior through `BindingContext`, bindings, commands, and events as appropriate.
5. Apply styles and templates, then verify behavior, accessibility, and deployment on the stated target platforms.

Distinguish a control's display name, such as DataGrid, from its API type, such as `RadDataGrid`. A XAML prefix is an alias, not a C# namespace. Verify C# namespaces and assembly references for each control instead of inferring them from the XML namespace.

Distinguish `BindingContext` on a view from the item context inside a `DataTemplate`. A `ControlTemplate` changes a control's visual structure; a `DataTemplate` defines item presentation. Do not substitute one for the other.

Use the following domain boundaries:

| Area | Required Distinction |
|---|---|
| Controls and layout | DataGrid displays tabular items; CollectionView displays item collections; TreeView displays hierarchical items. Verify each control's own APIs and layout constraints. |
| Data binding and MVVM | Explain `ItemsSource`, `BindingContext`, binding paths, change notifications, and item contexts. `ObservableCollection<T>` notifies collection changes; item-property changes require their own notification mechanism. |
| Commands and events | Distinguish `ICommand` execution and `CanExecute` from event handlers. Identify the specific control command and parameter type rather than assuming a shared command API. |
| Behaviors and triggers | Behaviors attach reusable logic; triggers react to state or property changes. Do not assume a behavior inherits a page's binding context. |
| Styles and resources | Use `Style` setters, resource dictionaries, `StaticResource`, and `DynamicResource` deliberately. Document scope, resource keys, and supported target properties. |
| Templates | Distinguish `DataTemplate`, `ControlTemplate`, and control-specific template properties. State the template binding context. |
| Navigation and DI | Shell Navigation is a framework feature. NavigationView is a Telerik control, not a Shell replacement API. Register application services and viewmodels through dependency injection where the scenario uses it. |
| Chart families | Select the Chart or Charts family used by the article and verify its series, axes, namespaces, and platform support. Do not combine examples from different generations. |
| Scheduling and dates | Scheduler displays and edits appointments where supported; Calendar supports date-oriented UI. Neither is an application background-job scheduler or notification delivery service. |
| Documents | PdfProcessing creates and manipulates PDF documents without providing a viewer UI. PDF Viewer displays PDF content; RichTextEditor edits rich text. Verify supported formats separately. |
| Deployment | State Android, iOS, Mac Catalyst, or Windows targets, the .NET and Telerik versions, and relevant build tools. Verify permissions, assets, trimming, AOT, and Release behavior when relevant. Do not assume platform parity. |
| Security and licensing | Follow the suite's release-specific license guidance. Keep license keys and feed credentials out of examples. UI visibility, barcode content, and client-side validation are not authorization boundaries. |

### Most Common Terms

| ❌ Avoid | ✅ Use | Notes |
|---|---|---|
| check box, Check Box | checkbox | One word, lowercase |
| data set | dataset | Use `DataSet` for the .NET API type |
| drop down, drop-down | dropdown | One word when used as a noun or adjective |
| dialog, dialogue | dialog box | Always "dialog box" (two words) when referring to a UI window |
| file name | filename | One word |
| name space | namespace | One word |
| tool bar | toolbar | One word |
| tool tip | tooltip | One word |
| work space | workspace | One word |
| plug in (noun) | plugin | One word as a noun; "plug in" as a verb (two words) |
| log in (noun) | login | One word as a noun; "log in" as a verb (two words) |
| set up (noun) | setup | One word as a noun; "set up" as a verb (two words) |
| back end (adj) | backend | One word as an adjective; varies by context as a noun |
| front end (adj) | frontend | One word as an adjective; varies by context as a noun |
| on-line | online | One word, no hyphen |
| off-line | offline | One word, no hyphen |
| e-mail | email | One word, no hyphen |
| web site | website | One word |
| web page | webpage | One word |

### Version and Comparison Terms

| ❌ Avoid | ✅ Use | Why |
|---|---|---|
| older version | earlier version | "Older" implies age, not sequence |
| newer version | later version | "Newer" implies recency, not sequence |
| lower version | earlier version | "Lower" implies rank, not sequence |
| higher version | later version | "Higher" implies rank, not sequence |
| since version 2.0 | starting with version 2.0 | "Since" is ambiguous (temporal or causal) |
| as of version 2.0 | starting with version 2.0 | Same ambiguity |

### Accessibility-Sensitive Terms

| ❌ Avoid | ✅ Use | Why |
|---|---|---|
| grayed-out or disabled (imprecise UI prose) | unavailable, or disabled when technically precise | Preserve accessibility state names and APIs such as `IsEnabled`; never obscure the actual state |
| grayed out | unavailable or dimmed | "Grayed out" is visual-only; inaccessible to screen readers |
| invalid (general prose) | not valid | Preserve exact API identifiers and diagnostic messages |

## Review Workflow and Expected Output

Follow this workflow for an article, support response, or sample prompt:

1. Identify the control or library, Telerik version, .NET version, target platforms, and article type from the available context.
2. Read the full article and the vocabulary reference. Check prose, metadata, examples, prompts, tables, captions, links, and checklists.
3. Correct brand names and interaction verbs. Keep the original task, section structure, and exact technical identifiers.
4. Check each domain claim against the matching repository article or official API documentation. Do not guess version support or invent a direct API equivalent.
5. Replace examples with realistic MAUI tasks. Verify XAML namespaces, C# types, binding contexts, setup, and platform assumptions. Keep Document Processing scenarios only when the article actually uses that library.
6. Verify that links resolve, local reference paths exist, and examples match the target component. Flag missing evidence rather than claiming an untested fix.
7. Apply the quick checklist and return the edited content with a concise summary of substantive changes and unresolved questions.

For a review-only request, report the location, original wording, correction, and reason. For an edit request, update the requested files directly. Do not create a separate summary file unless requested.

State what was verified and what still needs runtime validation. A terminology correction alone does not prove that XAML compiles, bindings resolve, a screen reader announces a control correctly, or an app deploys successfully.

### Sample Prompts and Expected Outcomes

Use these examples as realistic review tasks:

| Sample Prompt | Expected Outcome |
|---|---|
| "Correct terminology in a DataGrid data-binding article." | Distinguish `ItemsSource`, page `BindingContext`, item properties, and change notifications. Preserve exact column APIs. |
| "Review a CollectionView item-template example." | Identify the item binding context, verify `DataTemplate` bindings, and distinguish Telerik `RadCollectionView` from the framework control. |
| "Review a PdfProcessing example used in a MAUI app." | Verify library-specific namespaces, format providers, stream handling, and platform restrictions. Do not describe PdfProcessing as a viewer. |
| "Correct a Scheduler appointments guide." | Describe appointment data and supported interactions, not background execution or email delivery. |
| "Review a NavigationView and Shell Navigation article." | Separate Telerik selection and content APIs from framework routes and navigation; verify DI setup where used. |

### Troubleshooting Decision Guide

Route terminology and technical claims by the failing layer:

| Symptom | Check and Describe | Do Not Recommend |
|---|---|---|
| A XAML type cannot be resolved | Package references, Telerik version, XML namespace, actual control type, and `UseTelerik()` registration. | Guess a namespace from another Telerik UI suite. |
| A control displays no items | `ItemsSource`, `BindingContext`, binding diagnostics, item paths, notifications, and layout bounds. | Treat `x:DataType` as a replacement for setting a binding context. |
| A command does not execute | Command binding context, `ICommand`, `CanExecute`, control command contract, and parameter type. | Invent an event-to-command property or ignore a false `CanExecute` result. |
| Styling or templating fails | Resource scope, keys, `TargetType`, supported setters, and template context. | Apply a template property from a different control or product. |
| Behavior differs across platforms | Target OS, device, framework and Telerik versions, input method, native behavior, and documented limitations. | Promise identical gestures or keyboard support on every platform. |
| An app fails only in Release | Sanitized build output, target framework, trimming or AOT settings, resources, permissions, and reproduction steps. | Disable security controls or trimming globally as a routine fix. |
| Assistive technology cannot identify an element | Accessible name, semantics, focus order, platform accessibility support, and actual screen-reader output. | Claim accessibility based only on screenshots or color contrast. |
| License warnings appear | Exact diagnostic, Telerik package version, activation method, and build environment. | Request license-key content or publish feed credentials. |

Request only sanitized diagnostics and minimal MAUI samples. Redact personal data, credentials, tokens, license keys, and sensitive application data before including them in examples.

## Quick Checklist

When reviewing an article for brand names and terminology, verify:

- [ ] First brand mention includes trademark symbol (Progress® Telerik®)
- [ ] Subsequent mentions use product name only, no trademark symbols
- [ ] No possessives with brand names (not "Telerik's")
- [ ] No pluralized trademarks
- [ ] Generic nouns after product names are lowercase ("`RadDataGrid` class")
- [ ] Desktop interactions: click (not "click on"), press, select, enter
- [ ] No "click on" — just "click"
- [ ] Mobile interactions: tap, swipe, spread, pinch
- [ ] Mixed content: "select" as universal verb
- [ ] Standard compound words: checkbox, dropdown, filename, namespace, tooltip
- [ ] Version comparisons: "earlier/later" not "older/newer/lower/higher"
- [ ] Accessibility language avoids visual-only descriptions and preserves precise state names
- [ ] Exact API identifiers, UI labels, configuration values, and quoted diagnostics remain unchanged
- [ ] Control names, C# types, XAML namespaces, and framework concepts are accurate
- [ ] Binding contexts, item templates, notifications, commands, and events are distinct
- [ ] Styles, resource dictionaries, behaviors, triggers, Shell Navigation, and DI have their correct roles
- [ ] Chart families, PDF Viewer, PdfProcessing, and RichTextEditor are not conflated
- [ ] Deployment, accessibility, gestures, and version claims match the stated platforms
- [ ] Scheduler appointment UI is not described as background-job infrastructure
- [ ] Security guidance preserves access controls and excludes secrets
- [ ] Licensing references match the installed Telerik UI for .NET MAUI release
- [ ] Examples and prompts are realistic, links resolve, and unverified behavior is explicitly flagged
- [ ] The edited document and concise change summary satisfy the requested output

## References

Use the repository documentation for the target release. These references support terminology checks, not blanket guarantees across versions:

* [MAUI vocabulary and distinctions](./references/vocabulary.md)
* [Control catalog and documentation entry points](../../../../introduction.md)
* [DataGrid setup, XAML, and data](../../../../controls/datagrid/getting-started.md)
* [Supported frameworks, platforms, and tools](../../../../installation/system-requirements.md)
* [NuGet package installation](../../../../installation/manual-installation-approaches/nuget/overview.md)
* [License setup](../../../../installation/licensing/set-up-your-license.md)
* [Document Processing library integration](../../../../integrations/document-processing-libraries.md)
* [CollectionView screen-reader support](../../../../controls/collectionview/accessibility/screen-reader.md)
* [CollectionView keyboard support on Windows](../../../../controls/collectionview/accessibility/keyboard-navigation/windows.md)
* [CollectionView keyboard support on Mac Catalyst](../../../../controls/collectionview/accessibility/keyboard-navigation/maccatalyst.md)
