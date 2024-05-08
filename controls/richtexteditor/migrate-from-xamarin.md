---
title: Migrating from Xamarin
page_title: .NET MAUI RichTextEditor Documentation - Migrate from Xamarin
description: Learn how to migrate from Xamarin.Forms RichTextEditor to .NET MAUI RichTextEditor control.
position: 20
slug: richtexteditor-migrate-from-xamarin
---

# Migrate from Xamarin.Forms RichTextEditor to .NET MAUI RichTextEditor

The tables in the following sections list the differences between the APIs of the Xamarin.Forms RichTextEditor and .NET MAUI RichTextEditor.
## Migrate the Namespaces

| Control | Control name | C# Namespace| XAML Namespcace |
| --------------- | --------------- | --------------- | --------------------------------------------------- |
| Xamarin RichTextEditor | `RichTextEditor` | xmlns:telerikRichTextEditor="clr-namespace:Telerik.XamarinForms.RichTextEditor;assembly=Telerik.XamarinForms.RichTextEditor" | using Telerik.XamarinForms.RichTextEditor; |
| .NET MAUI RichTextEditor | `RadRichTextEditor` |  xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |
| Xamarin RichTextEditorToolbar | `RadRichTextEditorToolbar` |  xmlns:telerikRichTextEditor="clr-namespace:Telerik.XamarinForms.RichTextEditor;assembly=Telerik.XamarinForms.RichTextEditor" | using Telerik.XamarinForms.RichTextEditor; |
| .NET MAUI RichTextEditorToolbar | `RadRichTextEditorToolbar` |  xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | Telerik.Maui.Controls.RichTextEditor; |

## API Changes

>important All toolbar items have `RichTextEditor` in front of the naming. For example:

| Xamarin RichTextEditor | .NET MAUI RichTextEditor |
| ------------- | --------------- |
| `BoldToolbarItem` | `RichTextEditorBoldToolbarItem` |
| `ClearFormattingToolbarItem` | `RichTextEditorClearFormattingToolbarItem` |
| `AddImageToolbarItem` | `RichTextEditorImageNavigationToolbarItem` |
| `AddHyperlinkToolbarItem ` | `RichTextEditorHyperlinkNavigationToolbarItem` |

> The .NET MAUI RichTextEditor Toolbar is a new toolbar that inherits from [Telerik .NET MAUI Toolbar]({%slug toolbar-overview%}).

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
