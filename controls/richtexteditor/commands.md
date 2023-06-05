---
title: Commands
page_title: .NET MAUI RichTextEditor Documentation - Commands
description: Check our &quot;Commands&quot; documentation article for Telerik RichTextEditor for .NET MAUI control.
position: 9
slug: richtexteditor-commands
---

# Commands

RichTextEditor provides the following commands of type `ICommand`.

| Commands | Description |
| ------------- | --------------- |
| `UndoCommand` | Gets a command to undo the last changes in the editor. |
| `RedoCommand` | Gets a command to redo the last changes in the editor. |
| `ToggleBoldCommand` | Gets a command to toggle the bold text in the editor. |
| `ToggleItalicCommand` | Gets a command to toggle the italic text in the editor. |
| `ToggleUnderlineCommand` | ets a command to toggle the underline text in the editor. |
| `ToggleStrikethroughCommand` | Gets a command to toggle the strike-through text in the editor. |
| `ToggleSubscriptCommand` | Gets a command to toggle the subscript text in the editor. |
| `ToggleSuperscriptCommand` | Gets a command to toggle the superscript text in the editor. |
| `ToggleBulletingCommand` | Gets a command to toggle the bullets paragraph in the editor. |
| `ToggleNumberingCommand` | Gets a command to toggle the bullets paragraph in the editor. |
| `ClearFormattingCommand` | Gets a command to clear the formatting of the text in the editor. |
| `AlignLeftCommand` | Gets a command to apply left text alignment in the editor. |
| `AlignRightCommand` | Gets a command to apply right text alignment in the editor. |
| `AlignCenterCommand` | Gets a command to apply center text alignment in the editor. |
| `AlignJustifyCommand` | Gets a command to apply justify text alignment in the editor. |
| `IndentCommand` | Gets a command to indent the text in the editor. |
| `OutdentCommand` | Gets a command to outdent the text in the editor. |
| `ApplyHyperlinkCommand` | Gets a command to apply a hyperlink in the editor. |
| `RemoveHyperlinkCommand` | Gets a command to remove a hyperlink in the editor. |
| `OpenHyperlinkCommand` | Gets a command to open a hyperlink in the editor. |
| `InsertImageCommand` | Gets a command to insert an image in the editor. The command takes a single paramerer of type `Telerik.Maui.Controls.RichTextEditor.RichTextImage`. |
| `RemoveImageCommand` | Gets a command to remove an image in the editor. |
| `SelectAllCommand` | Gets a command to select all html in the editor. |

>note RadRichTextEditor Toolbar exposes some of the commands built-in. For more information please check the [RadRichTextEditor Toolbar]({%slug richtexteditor-toolbar%}) article.

## Example

Through the provided commands you can execute the corresponding actions over RichTextEditor (for example apply bold text formatting) from a custom UI other than the RichTextEditor toolbar. 

Following is an example how the RadRichTextEditor commands could be called on a button click action. 

Let's add the RichTextEditor definition together with a few sample buttons wired to the editor's commands:

<snippet id='richtexteditor-commands-xaml' />

Add the required namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

>important For the RichTextEditor Commands example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) RichTextEditor -> Features category.

## See Also

- [RadRichTextEditor Toolbar]({%slug richtexteditor-toolbar%})
