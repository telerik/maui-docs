---
title: Configuration
page_title: .NET MAUI RichTextEditor Documentation - Configuration
description: Check our &quot;Configuration&quot; documentation article for Telerik RichTextEditor for .NET MAUI control.
position: 3
slug: richtexteditor-configuration
---

# Configuration

The purpose of this help article is to show you the key features of the RichTextEditor.

## HTML Source options

RichTextEditor exposes `Source` property of type `RichTextSource`&mdash;Used to load HTML content into the editor from a string as well as from a stream. 

You can directly assign a string (containing HTML) as a <code>Source</code> of the editor - RadRichTextEditor will properly display the HTML content through the implemented in RichTextSource implicit converter. Check a simple example on this below:

```C#
this.richTextEditor.Source = "<b>Hello World!</b>";
```

### Load HTML from a string

You can easily load the HTML content from a string by using the static <code>FromString</code> method of the **RichTextSource** class and assigning the result to the **Source** property of RadRichTextEditor:

<snippet id='richtexteditor-getting-started' />

Alternatively, you can create a [RichTextHtmlStringSource](/devtools/xamarin/api/telerik.xamarinforms.richtexteditor.richtexthtmlstringsource) object and assign it to the <code>Source</code> property of the RichTextEditor.

### Load HTML from a stream

Another option to preload HTML is by retrieving it from a stream through the static <code>FromStream</code> method of the **RichTextSource** and again,  assign the result to the **Source** property of the RichTextEditor:

<snippet id='richtexteditor-keyfeatures-fromstream' />

>note In the example the HTML file is loaded as an `EmbeddedResource` 

Alternatively, you can create a [RichTextHtmlStreamSource](/devtools/xamarin/api/telerik.xamarinforms.richtexteditor.richtexthtmlstreamsource) object and set it as the <code>Source</code> of the RichTextEditor.

## Retrieving HTML Content

Through `GetHtmlAsync` method of RichTextEditor you can obtain the created and updated inside the editor HTML content:

<snippet id='richtexteditor-keyfeatures-gethtml' />

And the result:

![.NET MAUI RichTextEditor GetHTML](images/rte-get-html.gif)

## RichText Editing Capabilities

RichTextEditor will help app users create and edit HTML content. You can apply provided by RichTextEditor editing features through the built-in UI, namely [RadRichTextEditorToolbar]({%slug richtexteditor-toolbar %}), or you can create custom UI and manually execute the RadRichTextEditor [Commands]({%slug richtexteditor-commands%}).

In addition, RichTextEditor provides flexible API to apply formatting at the current caret position or on the selected text inside the editing area.

| Formating options | Descriptions |
| ------------- | --------------- |
| `TextFormatting` of type `RichTextFormatting` | Defines the text formatting, such as heading, paragraph or quotation of the text at the current position or selection. |
| `TextColor` | Specifies the color of the text at the current position or selection; |
| `HighlightTextColor` | Defines the text background color at the current position or selection; |
| `SelectionRange` of type `RichTextSelectionRange` | Specifies the start and end position of the currently selected inside the editor text. |
| `FontSize` | Sets the font size of the text at the current caret position or selection; |
| `FontAttributes` of type `RichTextFontAttributes` | Defines the font attributes, such as bold, italic, subscript and superscript at the current position or selection; |
| `TextDecorations` of type `RichTextDecorations` | Specifies text decorations, such as underline and strikethrough at the current position or selection; |
| `HorizontalTextAlignment` of type `RichTextHorizontalAlignment` | Specifies the text alignment, such as left, right, center or justify at the current position or selection; |
| `ListType` of type `RichTextListType` | Specifies the list type, such as numbered or bulleted list at the current position or selection. |

## Text Selection

RichTextEditor supports text selection functionality - the end user can initiate a selection action through the tap and hold gesture over the text. The selected text is marked with a different background color and two drag handles are available to the user to make it easier to modify the current selection. 

* `GetSelectionAsync` method - returns asynchronously a RichTextSelection object which defines the current text selection inside the editor (*null* if there is no text selection). The <code>RichTextSelection</code> object contains the `Text` itself as well as the `Start` and `End` position of the text characters;
	
## Read-Only State

`IsReadOnly`(`bool`) property of the RichTextEditor indicating whether the control is in a read-only mode. Setting `IsReadOnly="True"` means that the Toolbar Items will be disabled, the content of the document cannot be changed and no selection can be performed. The default the value is `False`. 

### Example

For the example we triggers the IsReadOnly State using a Switch. Here is the XAML Definition:

<snippet id='richtexteditor-readonly-state' />

For the example we use a converter to hide the Toolbar when the control is in read-only state:

<snippet id='richtexteditor-readonly-converter' />

Defining the Source of the RichTextEditor:

<snippet id='richtexteditor-readonly-state-code-behind' />

> The richtexteditor-htmlsource.html file is visualized in the Editor as an EmbeddedResource.

>important For the RichTextEditor Read Only state example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) RichTextEditor -> Features category.

## See Also

- [RadRichTextEditor Toolbar]({%slug richtexteditor-toolbar%})
- [Commands]({%slug richtexteditor-commands%})
- [Configure the RichTextEditor]({%slug richtexteditor-configuration%})
- [Events]({%slug richtexteditor-events%})
- [Working with images]({%slug richtexteditor-images-overview%})
- [Hyperlinks]({%slug richtexteditor-hyperlink-support%})
