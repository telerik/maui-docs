---
title: Context Menu
page_title: .NET MAUI RichTextEditor Documentation - Context Menu
description: Learn more about the options for adding and customizing the context menu in the Telerik UI for .NET MAUI RichTextEditor control.
position: 10
slug: richtexteditor-context-menu
---

# Events

The .NET MAUI RichTextEditor a built-in context menu support which shows common operations such as Copy and Paste for sharing data between the apps or within the app. On WinUI and MacCatalyst the context menu opens on right-button click over the editor content. On Android and iOS it is also displayed as soon as the user performs selection.

The default context menu shows the following options:

* Cut&mdash;Cuts the selected content and saves it in the system clipboard;
* Copy&mdash;Copies the selected content and saves it in the clipboard;
* Paste&mdash;Pastes the content from the clipboard into the editor;
* Paste as Plain Text&mdash;Pastes the content from the clipboard stripping any additional formatting;
* Select All&mdash;Selects all of the content in the editor;

What options are available in the context menu depends on the current content selection or caret position in the editor.

## Custom Context Menu

You can easily modify the RichTextEditor default context menu and add or remove some of the provided options. Just need to set `AutoGenerateContextMenu` property of the RichTextEditor to `False` and manually define the ContextMenuItems. You can choose from the predefined ContextMenuItems or create a `CustomContextMenuItem` instance and define its `Text` and `Command` (the `Command` can be bound to any of the RadRichTextEditor's [Commands]({%slug richtexteditor-commands%}) or to a custom command). 

The table below shows the predefined ContextMenuItems:

| Context Menu Item | Description |
| ----- | ---------- |
| `RichTextEditorBoldContextMenuItem` | Represents the toggle bold context menu item that executes the Bold command |
| `RichTextEditorCopyContextMenuItem` | Represents the copy context menu item that executes the Copy command |
| `RichTextEditorCutContextMenuItem` | Represents the cut context menu item that executes the Cut command |
| `RichTextEditorPasteContextMenuItem` | Represents the paste context menu item that executes the Paste command |
| `RichTextEditorPastePlainTextContextMenuItem` | Represents the paste as plain text context menu item that executes the Paste command |
| `RichTextEditorSelectAllContextMenuItem` | Represents the select all text context menu item that executes the SelectAll command |
| `RichTextEditorItalicContextMenuItem` | Represents the toggle italic context menu item that executes the Italic command |
| `RichTextEditorOpenHyperlinkContextMenuItem` | Represents the open hyperlink context menu item that executes the OpenHyperlinc command |
| `RichTextEditorCustomContextMenuItem` | Represents a custom context menu item that allows setting the Text, Command and CommandParameter. |

This is an example how the RichTextEditor context menu can be customized:

**1.** Define the RichTextEditor with the `ContextMenuItems`

<snippet id='richtexteditor-contextmenu-xaml' />

**2.** Add the `telerik` namespaces:

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