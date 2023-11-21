---
title: Configuration
page_title: .NET MAUI RichTextEditor Documentation - Configuration
description: Check our &quot;Configuration&quot; documentation article for Telerik RichTextEditor for .NET MAUI control.
position: 3
slug: richtexteditor-configuration
---

# Configuration

By using the exposed configuration options of the .NET MAUI RichTextEditor, you can configure the component features, such as the HTML source, text formatting options, text selections, and the read-only mode.

## HTML Source Options

To load HTML content from a string or a stream into the editor, use the `Source` property of type `RichTextSource`. 

You can directly assign a string (containing HTML) as a <code>Source</code> of the editor and `RadRichTextEditor` will display the HTML content through the implicit converter implemented in `RichTextSource`.

```C#
this.richTextEditor.Source = "<b>Hello World!</b>";
```

### Load HTML from a String

You can load the HTML content from a string by using the static <code>FromString</code> method of the `RichTextSource` class and assign the result to the `Source` property of `RadRichTextEditor`:

<snippet id='richtexteditor-getting-started' />

Alternatively, you can create a [`RichTextHtmlStringSource`](/devtools/maui/api/telerik.maui.controls.richtexteditor.richtexthtmlstringsource) object and assign it to the <code>Source</code> property of the RichTextEditor.

### Load HTML from a Stream

Another option to preload HTML is by retrieving it from a stream through the static <code>FromStream</code> method of the `RichTextSource` and again, assign the result to the `Source` property of the RichTextEditor. In the example below, the HTML file is loaded as an `EmbeddedResource`.

<snippet id='richtexteditor-keyfeatures-fromstream' />

Alternatively, you can create a [`RichTextHtmlStreamSource`](/devtools/maui/api/telerik.maui.controls.richtexteditor.richtexthtmlstreamsource) object and set it as the <code>Source</code> of the RichTextEditor.

## Retrieving HTML Content

Through `GetHtmlAsync` method of RichTextEditor, you can get the content created and updated inside the editor HTML:

<snippet id='richtexteditor-keyfeatures-gethtml' />

The next image shows the result from the sample code with `GetHtmlAsync`.

![.NET MAUI RichTextEditor GetHTML](images/rte-get-html.gif)

## RichTextEditor Editing Capabilities

RichTextEditor helps the app users to create and edit HTML content. You can apply the editing features provided by RichTextEditor through the UI by using the[`RadRichTextEditorToolbar`]({%slug richtexteditor-toolbar %}), or you can create your custom UI and manually execute the `RadRichTextEditor` [Commands]({%slug richtexteditor-commands%}).

In addition, RichTextEditor provides a flexible API that allows you to apply formatting at the current caret position or on the selected text inside the editing area.

| Formating Options | Descriptions |
| ------------- | --------------- |
| `TextFormatting` of type `RichTextFormatting` | Defines the text formatting, such as heading, paragraph or quotation of the text at the current position or selection |
| `TextColor` | Specifies the color of the text at the current position or selection |
| `HighlightTextColor` | Defines the text background color at the current position or selection |
| `SelectionRange` of type `RichTextSelectionRange` | Specifies the start and end position of the currently selected inside the editor text |
| `FontSize` | Sets the font size of the text at the current caret position or selection |
| `FontAttributes` of type `RichTextFontAttributes` | Defines the font attributes, such as bold, italic, subscript, and superscript at the current position or selection |
| `TextDecorations` of type `RichTextDecorations` | Specifies text decorations, such as underline and strikethrough at the current position or selection |
| `HorizontalTextAlignment` of type `RichTextHorizontalAlignment` | Specifies the text alignment, such as left, right, center, or justify at the current position or selection |
| `ListType` of type `RichTextListType` | Specifies the list type, such as numbered or bulleted list at the current position or selection |

## Text Selection

RichTextEditor has a text selection functionality—the end user can initiate a selection action through the tap and hold gesture over the text. The selected text is marked with a different background color and two drag handles are available to the user to make it easier to modify the current selection. 

* `GetSelectionAsync` method—Asynchronously returns a `RichTextSelection` object which defines the current text selection inside the editor (returns `null` if no text is selected). The <code>RichTextSelection</code> object contains the `Text` itself as well as the `Start` and `End` position of the text characters.
	
## Read-Only State

The `IsReadOnly`(`bool`) property of the RichTextEditor indicates whether the control is in a read-only mode. Setting `IsReadOnly="True"` means that the Toolbar Items will be disabled, the content of the document cannot be changed, and no selection can be performed. The default the value is `False`. 

### Read-Only Example

The next example shows how to triggers the `IsReadOnly` state by using a switch. The next snippet shows the XAML definition:

<snippet id='richtexteditor-readonly-state' />

For the example, we use a converter to hide the Toolbar when the control is in read-only state:

<snippet id='richtexteditor-readonly-converter' />

The next code sample shows how to define the source of the RichTextEditor:

<snippet id='richtexteditor-readonly-state-code-behind' />

> The `richtexteditor-htmlsource.html` file is visualized in the Editor as an `EmbeddedResource`.

> For a runnable example with the RichTextEditor read-only state, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **RichTextEditor > Features**.


## See Also

- [RadRichTextEditor Toolbar]({%slug richtexteditor-toolbar%})
- [Commands]({%slug richtexteditor-commands%})
- [Configure the RichTextEditor]({%slug richtexteditor-configuration%})
- [Events]({%slug richtexteditor-events%})
- [Working with images]({%slug richtexteditor-images-overview%})
- [Hyperlinks]({%slug richtexteditor-hyperlink-support%})
