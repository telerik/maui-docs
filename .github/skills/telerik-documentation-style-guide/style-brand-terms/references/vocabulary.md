# Telerik UI for .NET MAUI Vocabulary Reference

Standard vocabulary, compound words, and terminology conventions for Telerik UI for .NET MAUI documentation and support guidance. Use this reference with the [brand and terminology skill](../SKILL.md).

Preserve exact API names, resource keys, UI labels, and quoted diagnostics even when they differ from prose conventions. Confirm feature and format availability for the Telerik release, .NET version, target platform, and build configuration.

## Table of Contents

- [Compound Words](#compound-words)
- [UI Element Names](#ui-element-names)
- [Technical Terms](#technical-terms)
- [Telerik UI for .NET MAUI Terms](#telerik-ui-for-net-maui-terms)
- [MAUI Architecture and Feature Boundaries](#maui-architecture-and-feature-boundaries)
- [Action Verbs (Desktop)](#action-verbs-desktop)
- [Action Verbs (Mobile)](#action-verbs-mobile)
- [Version and Comparison Language](#version-and-comparison-language)
- [Accessibility-Sensitive Terms](#accessibility-sensitive-terms)
- [Commonly Confused Terms](#commonly-confused-terms)
- [Validation and Troubleshooting Terms](#validation-and-troubleshooting-terms)
- [References](#references)

## Compound Words

These terms have settled spellings in technical writing. Use the standard form consistently.

| Standard Form | ❌ Avoid These Variants |
|---|---|
| checkbox | check box, check-box, Check Box |
| dataset | data set, data-set (use `DataSet` for the .NET API type) |
| database | data base, data-base |
| dropdown | drop down, drop-down (as noun/adjective) |
| email | e-mail, E-mail |
| filename | file name, file-name |
| frontend | front end, front-end (as adjective) |
| backend | back end, back-end (as adjective) |
| login | log in, log-in (as noun/adjective) |
| namespace | name space, name-space |
| offline | off-line |
| online | on-line |
| plugin | plug in, plug-in (as noun) |
| popup | pop up, pop-up (as noun/adjective) |
| setup | set up, set-up (as noun/adjective) |
| stylesheet | style sheet, style-sheet |
| toolbar | tool bar, tool-bar |
| tooltip | tool tip, tool-tip |
| username | user name, user-name |
| webpage | web page, web-page |
| website | web site, web-site |
| workflow | work flow, work-flow |
| workspace | work space, work-space |

**Note on verb forms**: Some compound words split when used as verbs:
- "Log in to the application" (verb) vs. "Enter your login credentials" (noun)
- "Set up the environment" (verb) vs. "Complete the setup process" (noun)
- "Plug in the device" (verb) vs. "Install the plugin" (noun)
- "Pop up on the screen" (verb) vs. "Close the popup window" (noun)

## UI Element Names

Use these standard names when referring to user interface elements:

| Standard Term | ❌ Avoid |
|---|---|
| dialog box | dialog, dialogue, dialog window, popup dialog |
| dropdown | drop down, drop-down (as noun/adjective); preserve ComboBox or another actual control name |
| context menu | right-click menu, popup menu |
| pane | panel when inaccurate; preserve exact framework type and UI names |
| tab | tabbed page, tab page |
| text box | edit box when inaccurate; use Entry, Editor, or the actual MAUI control name when identifying a control |
| checkbox | check box, tick box |
| radio button | option button, radio control |
| scrollbar | scroll bar, scroll-bar |
| menu bar | menubar, menu-bar |
| status bar | statusbar, status-bar |
| tooltip | tool tip, hover text, hint |
| progress bar | progress indicator, loading bar |
| breadcrumb | breadcrumb trail, navigation path |

## Technical Terms

Standard forms for common technical terms:

| Standard Term | ❌ Avoid | Notes |
|---|---|---|
| API | api, Api | Always uppercase |
| URL | url, Url | Always uppercase |
| XML | xml, Xml | Always uppercase |
| JSON | json, Json | Always uppercase |
| HTML | html, Html | Always uppercase |
| CSS | css, Css | Always uppercase |
| SQL | sql, Sql | Always uppercase |
| PDF | pdf, Pdf | Always uppercase |
| .NET | .net, .Net, dotnet | Capital NET with leading dot |
| .NET MAUI | .NET Maui, MAUI.NET | Framework name; distinguish it from the Telerik suite |
| XAML | xaml, Xaml in prose | Preserve the case of exact identifiers and language fence aliases |
| C# | C Sharp, c# in prose | Use C# for application examples |
| MVVM | Mvvm, mvvm in prose | Model-View-ViewModel; do not imply a specific MVVM package is required |
| NuGet | nuget, Nuget, NuGET | Specific casing |
| GitHub | Github, github, GITHUB | Specific casing |
| JavaScript | Javascript, javascript, JAVASCRIPT | Specific casing |
| TypeScript | Typescript, typescript | Specific casing |
| Boolean | Inconsistent prose capitalization | Use `bool` in C# or the exact API type, such as `System.Boolean` |
| null | Changed casing in copied code | Use `null` in C# and the appropriate XAML null markup where needed |
| true/false | Changed casing in copied code | Preserve C# `true`/`false` and the Boolean syntax used by the XAML sample |

## Telerik UI for .NET MAUI Terms

Use these terms for MAUI control and application documentation. Display names are not interchangeable with API identifiers:

| Standard Term | Meaning and Usage |
|---|---|
| Telerik UI for .NET MAUI | The Telerik native cross-platform UI suite. Use Progress® Telerik® UI for .NET MAUI on first brand mention in customer-facing body prose, not in headings, metadata, or code. |
| .NET MAUI | Microsoft's framework for native cross-platform applications. macOS apps use Mac Catalyst; Windows apps use WinUI. Verify currently supported targets in system requirements. |
| DataGrid | Tabular data control; `RadDataGrid` is its API type. `ItemsSource` supplies items, not a database connection. |
| CollectionView | Telerik item collection control; use `RadCollectionView` to distinguish it from Microsoft `CollectionView` in API discussions. |
| TreeView | Hierarchical item control. Describe nodes, children, expansion, and selection using its documented APIs. |
| Chart / Charts | Separate documentation families in this repository. Name the family and verify its types, series, axes, and supported platforms. |
| Scheduler | Appointment UI control, not an operating-system background scheduler. |
| Calendar | Date-oriented UI control. Do not assume it exposes Scheduler appointment-editing APIs. |
| DataForm | Data editing control with editors and validation. Validation in the UI is not server-side authorization. |
| Barcode | Barcode generation control. Document the symbology and supported value format; do not promise scanning functionality. |
| NavigationView | Telerik navigation UI control. Distinguish its items and content from Shell routes. |
| RichTextEditor | Rich-text editing control. Verify its supported content formats and platform behavior. |
| PDF Viewer | Control for displaying PDF content. Do not call it PdfProcessing. |
| PdfProcessing | Document Processing library for creating and manipulating PDF documents; it is not a XAML control. |
| XAML namespace | The suite uses `http://schemas.telerik.com/2022/xaml/maui`, commonly with the `telerik` prefix. It is not a C# namespace or a URL to download. |
| `UseTelerik()` | Control registration extension called in `MauiProgram.CreateMauiApp`; follow the setup article's imports and package requirements. |
| `BindingContext` | Source context for bindings on a bindable object. Item templates usually bind to an item, not the page viewmodel. |
| `ItemsSource` | Collection supplied to a control. The control does not automatically implement application data retrieval or persistence. |
| `x:DataType` | Declares the binding source type for compiled bindings; it does not instantiate a viewmodel or assign `BindingContext`. |
| MVVM | Separates views, viewmodels, and models. Specify any toolkit dependency rather than implying it is built into Telerik controls. |
| Command | An action represented by `ICommand` or a control-specific command contract. Preserve the command's parameter and execution semantics. |
| Event | A notification with a documented handler signature; not automatically an MVVM command. |
| Behavior | Reusable logic attached to a bindable object. Verify its binding context explicitly. |
| Trigger | Declarative reaction to a property, data, or event condition where supported. |
| Resource dictionary | Keyed resources used by pages, controls, or the app. Preserve the exact `ResourceDictionary` API identifier. |
| Style | A `Style` applies setters to a target type. It is not a control's entire visual template. |
| Data template | A `DataTemplate` defines an item's presentation. |
| Control template | A `ControlTemplate` defines visual structure where the control supports it. |
| Shell Navigation | Framework route-based navigation; not a Telerik control API. |
| Dependency injection | Registration and resolution of application services, pages, and viewmodels through the app's service container. |

## MAUI Architecture and Feature Boundaries

Use these distinctions when adapting workflows and examples:

| Area | MAUI-Specific Guidance |
|---|---|
| Setup | Verify NuGet package versions, workloads, license activation, `UseTelerik()`, and required imports before showing control markup. |
| Data changes | `ObservableCollection<T>` notifies collection changes; `INotifyPropertyChanged` or an equivalent mechanism notifies item-property changes. Describe UI-thread requirements for the scenario. |
| Binding contexts | Distinguish page, control, item, and template contexts. Check binding paths, converters, and `x:DataType` rather than guessing why a binding is empty. |
| Commands and events | Verify command type, binding source, parameters, `CanExecute`, and event signatures against the specific control API. |
| Layout and virtualization | Give virtualized controls bounded space; verify each control's documented layout guidance. A `ScrollView` is not a universal fix for missing items. |
| Styling and templating | State resource scope, keys, target type, setters, and template context. Do not assume `StaticResource` and `DynamicResource` are interchangeable. |
| Framework features | Identify behaviors, triggers, Shell Navigation, and dependency injection as framework or application patterns unless a documented Telerik API supplies the feature. |
| Document Processing | Verify package, namespace, format provider, stream lifetime, font requirements, and target-platform support. UI controls and document libraries have different responsibilities. |
| Cross-platform deployment | Name Android, iOS, Mac Catalyst, and Windows only as supported by the target release. Check platform permissions, assets, trimming, AOT, and native tool requirements where relevant. |
| Accessibility | Verify accessible names, semantics, focus order, keyboard behavior where supported, scaling, and contrast. Test with the target platform's assistive technology before claiming compliance. |
| Localization | Separate text localization, culture-sensitive formatting, and right-to-left layout. Verify the control's localization resources and platform support. |
| Security | Enforce authorization in the application or service layer. Validate external input, protect credentials, and use sanitized sample data. Hiding UI does not protect data. |
| Licensing | Follow the suite's license activation documentation for the installed release and build environment. Never request or reproduce a license key. |

Keep credentials, license keys, access tokens, and sensitive application data out of XAML, C#, logs, screenshots, prompts, and expected outputs.

## Action Verbs (Desktop)

Use the exact label from the target control, IDE, or sample app. These examples illustrate terminology, not a universal UI layout:

| User Action | Verb | Example |
|-------------|------|---------|
| Activate a button | click | Click **Add** in the sample app. |
| Activate with two clicks | double-click | Double-click `MainPage.xaml` in Visual Studio. |
| Activate with secondary button | right-click | Right-click the project in **Solution Explorer**. |
| Press a keyboard key | press | Press `Ctrl`+`S`. |
| Choose from menu | select | Select **File** > **Open**. |
| Choose from dropdown | select | Select a country in the ComboBox. |
| Mark a checkbox | select | Select the **Show Details** checkbox in the sample app. |
| Unmark a checkbox | clear | Clear the **Show Details** checkbox in the sample app. |
| Enter text | enter, type | Enter a name in the DataForm editor. |
| Move by dragging | drag | Drag a DataGrid column boundary when resizing is enabled. |
| Hover over an element | point to | Point to the icon to see the tooltip. |
| Expand a tree node | expand | Expand the TreeView parent item. |
| Collapse a tree node | collapse | Collapse the TreeView parent item. |

## Action Verbs (Mobile)

Confirm gesture support in the target control, platform, and version before writing instructions. For mixed desktop and mobile content, use "select" for activation:

| User Action | Verb | Example |
|-------------|------|---------|
| Activate an element | tap | Tap a date in the Calendar. |
| Activate with two taps | double-tap | Use only for documented double-tap behavior. |
| Move an element | drag | Use only for a supported and enabled control action. |
| Swipe | swipe | Describe the supported scroll or navigation action. |
| Zoom in | spread | Use only if the control supports this gesture. |
| Zoom out | pinch | Use only if the control supports this gesture. |
| Long press | press and hold | Use only for documented touch-and-hold behavior. |

## Version and Comparison Language

| ❌ Avoid | ✅ Use | Reason |
|---|---|---|
| older version | earlier version | Versions have sequence, not age |
| newer version | later version | Versions have sequence, not recency |
| lower version | earlier version | Versions have sequence, not rank |
| higher version | later version | Versions have sequence, not rank |
| since version X | starting with version X | "Since" can mean "because" |
| as of version X | starting with version X | Ambiguous |
| deprecated since | deprecated starting with, deprecated in | Clearer |

## Accessibility-Sensitive Terms

| ❌ Avoid | ✅ Use | Reason |
|---|---|---|
| disabled (imprecise UI prose) | unavailable, or disabled when technically precise | Preserve accessibility states and APIs such as `IsEnabled` |
| grayed out | unavailable, dimmed | Visual-only description |
| invalid input (general prose) | not valid, incorrect | Preserve exact diagnostic messages and API names |
| normal mode | default mode, standard mode | "Normal" implies other modes are abnormal |
| whitelist | allowlist | Inclusive language |
| blacklist | blocklist, denylist | Inclusive language |
| master/slave | primary/secondary, main/replica | Inclusive language |
| sanity check | smoke test, validation check | Inclusive language |
| dummy | placeholder, sample | Inclusive language |

## Commonly Confused Terms

| Term A | Term B | Difference |
|--------|--------|------------|
| log in (verb) | login (noun/adj) | "Log in to the app" vs. "the login page" |
| set up (verb) | setup (noun/adj) | "Set up the environment" vs. "the setup wizard" |
| back up (verb) | backup (noun/adj) | "Back up the data" vs. "the backup file" |
| roll back (verb) | rollback (noun/adj) | "Roll back the changes" vs. "the rollback procedure" |
| that | which | "that" for restrictive clauses, "which" for non-restrictive (with comma) |
| fewer | less | "Fewer" for countable nouns, "less" for uncountable |
| affect | effect | "Affect" = verb (to influence), "Effect" = noun (the result) |
| ensure | insure | "Ensure" = make certain, "Insure" = insurance |
| its | it's | "Its" = possessive, "It's" = it is (but don't use contractions with "it's") |
| `BindingContext` | `ItemsSource` | Binding context supplies a binding source; items source supplies a control's collection. |
| `x:DataType` | `BindingContext` | A binding type declaration does not assign a runtime source object. |
| Collection change | Item-property change | Collection notifications and property notifications serve different purposes. |
| `DataTemplate` | `ControlTemplate` | Item presentation and control visual structure are different contracts. |
| Command | Event | An executable action and a notification are not interchangeable APIs. |
| NavigationView | Shell Navigation | Telerik navigation UI and framework route navigation are distinct. |
| Scheduler | Background scheduling | Appointment UI does not automatically run background jobs or notifications. |
| PDF Viewer | PdfProcessing | A UI control displays documents; a library creates and manipulates them. |
| Telerik `RadCollectionView` | Microsoft `CollectionView` | Similar display names do not imply identical APIs or behavior. |

## Validation and Troubleshooting Terms

Describe the failing layer and the evidence instead of using a general phrase such as "the control is broken":

| Term or Symptom | Evidence to Request or Verify |
|---|---|
| XAML or build failure | Exact sanitized diagnostic, Telerik package version, target framework, namespace, setup, and referenced types. |
| Binding failure | `BindingContext`, `ItemsSource`, binding path, item type, notifications, and binding diagnostics. |
| Command failure | Binding source, command contract, parameter type, `CanExecute`, and event-to-command bridge if explicitly used. |
| Layout or template failure | Parent constraints, resource scope, target type, template property, and template binding context. |
| Platform-specific failure | OS and device, .NET and Telerik versions, input method, documented limitations, and minimal reproduction. |
| Release-only failure | Target framework, trimming or AOT configuration, resources, permissions, and sanitized build or crash output. |
| Accessibility issue | Accessible name, semantic properties, focus order, keyboard path where supported, scaling, and screen-reader observations. |
| License warning | Exact diagnostic, package version, activation method, and build environment. Never request the license key itself. |

Use "verified" only for checks actually performed. State when XAML compilation, C# compilation, binding behavior, assistive-technology testing, or platform deployment remains untested.

## References

Use the [skill's source references](../SKILL.md#references) for the control catalog, setup, packages, licensing, Document Processing, and platform accessibility. Consult the specific control's article and official API reference for bindings, commands, styling, localization, and platform limitations. Check these sources against the customer's version before making compatibility claims.
