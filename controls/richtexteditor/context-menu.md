---
title: Context Menu
page_title: .NET MAUI RichTextEditor Documentation - Context Menu
description: Learn more about the options for adding and customizing the context menu in the Telerik UI for .NET MAUI RichTextEditor control.
position: 10
slug: richtexteditor-context-menu
---

# Context Menu

The .NET MAUI RichTextEditor comes with a built-in context menu, which provides access to common operations, such as **Copy** and **Paste**, and enables the user to move content between apps or within an app. 

On WinUI and MacCatalyst, the context menu opens on a right-button click over the editor's content. On Android and iOS, it appears as soon as the user performs selection.

The default context menu shows the following options:

* **Cut**&mdash;Cuts the selected content and saves it in the system clipboard.
*  **Copy**&mdash;Copies the selected content and saves it in the clipboard.
*  **Paste**&mdash;Pastes the content from the clipboard into the editor.
*  **Paste as Plain Text**&mdash;Pastes the content from the clipboard by stripping any additional formatting.
*  **Select All**&mdash;Selects all of the content in the editor.

What options are available in the context menu depends on the current content selection or caret position in the editor.

## Custom Context Menu

You can modify the default context menu and add or remove some of the provided options by setting the `AutoGenerateContextMenu` property of the RichTextEditor to `False` and manually defining the context menu items. You can choose from the predefined items or create a `CustomContextMenuItem` instance and define its `Text` and `Command` (the `Command` can be bound to any of the `RadRichTextEditor` [Commands]({%slug richtexteditor-commands%}) or to a custom command).

The table below shows the predefined context menu items:

| Context Menu Item | Description |
| ----- | ---------- |
| `RichTextEditorBoldContextMenuItem` | Represents the **Bold** context menu item that executes the `Bold` command |
| `RichTextEditorCopyContextMenuItem` | Represents the **Copy** context menu item that executes the `Copy` command |
| `RichTextEditorCutContextMenuItem` | Represents the **Cut** context menu item that executes the `Cut` command |
| `RichTextEditorPasteContextMenuItem` | Represents the **Paste** context menu item that executes the `Paste` command |
| `RichTextEditorPastePlainTextContextMenuItem` | Represents the **Paste as plain text** context menu item that executes the `Paste` command |
| `RichTextEditorSelectAllContextMenuItem` | Represents the **Select all** text context menu item that executes the `SelectAll` command |
| `RichTextEditorItalicContextMenuItem` | Represents the **Italic** context menu item that executes the `Italic` command |
| `RichTextEditorOpenHyperlinkContextMenuItem` | Represents the **Open hyperlink** context menu item that executes the `OpenHyperlink` command |
| `RichTextEditorCustomContextMenuItem` | Represents a custom context menu item that allows setting the text, command, and command parameter. |

This example shows how to customize the RichTextEditor context menu:

**1.** Define the RichTextEditor with the context menu items:

<snippet id='richtexteditor-contextmenu-xaml' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the following view model for the custom command for the `RichTextEditorCustomContextMenuItem`:

<snippet id='richtexteditor-contextmenu-vm' />

> For a runnable example with the RichTextEditor Custom Context menu scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **RichTextEditor > Features** category.

## See Also

- [Commands]({%slug richtexteditor-commands%})
- [Configure the RichTextEditor]({%slug richtexteditor-configuration%})
- [Working with images]({%slug richtexteditor-images-overview%})
- [Hyperlinks]({%slug richtexteditor-hyperlink-support%})