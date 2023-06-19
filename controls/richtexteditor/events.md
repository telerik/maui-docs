---
title: Events
page_title: .NET MAUI RichTextEditor Documentation - Events
description: Check our &quot;Events&quot; documentation article for Telerik RichTextEditor for .NET MAUI control.
position: 10
slug: richtexteditor-events
---

# Events

The .NET MAUI RichTextEditor emits a set of events that allow you to configure the component's behavior in response to specific user actions.

The RichTextEditor component exposes the following events:

* `OpenHyperlinkError`&mdash;Raised when users try to open invalid URLs in the editor. The OpenHyperlinkError event handler receives two parameters:

	* The <code>Sender</code>, which is the RichTextEditor control;
	* `OpenHyperlinkErrorEventArgs`, which provides the following properties:
		* <code>Error</code>&mdash;of type `System.Exception`; can be used to get the exact error message;
		* <code>Url</code>&mdash;of type string; defines the URL of the hyperlink;
		* <code>Handled</code>&mdash;a boolean property indicating whether the event is handled.
		
* `IsReadOnlyChanged`&mdash;Raised when read-only mode of the RichTextEditor is switched. The `IsReadOnlyChanged` event receives two parameters:

	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<bool>`&mdash;provides the <code>NewValue</code> and <code>OldValue</code> properties of type `bool`, indicating the `IsReadOnly` property change.
			
* `FontFamilyChanged`&mdash;Raised when the <code>FontFamily</code> property of the RichTextEditor is modified. The `FontFamilyChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<string>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `FontSizeChanged`&mdash;Raised when the <code>FontSize</code> property of the RichTextEditor is modified. The `FontSizeChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextUnit>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.
	
* `FontAttributesChanged`&mdash;Raised when the <code>FontAttributes</code>, such as bold, italic, subscript and superscript is modified. The FontAttributesChanged event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextFontAttributes>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.
	
* `TextDecorationsChanged`&mdash;Raised when the <code>TextDecorations</code>, such as underline and strikethrough is modified. The `TextDecorationsChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextDecorations>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `TextFormattingChanged`&mdash;Raised when the <code>TextFormatting</code>, such as such as heading, paragraph or quotation is modified. The `TextFormattingChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextFormatting>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `HorizontalTextAlignmentChanged`&mdash;Raised when the <code>HorizontalTextAlignment</code>, such as left, right, center or justify is modified. The `HorizontalTextAlignmentChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextHorizontalAlignment>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `ListTypeChanged`&mdash;Raised when the <code>ListType</code>, such as numbered or bulleted list is modified. The `ListTypeChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextListType>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `TextColorChanged`&mdash;Raised when the <code>TextColor</code> property of the RichTextEditor is updated. The `TextColorChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<Color>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `HighlightTextColorChanged`&mdash;Raised when the <code>HighlightTextColor</code> property of the RichTextEditor is updated. The `HighlightTextColorChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<Color>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.
	
* `SelectionRangeChanged`&mdash;Raised when the <code>SelectionRange</code>, which defines the start and end position of the currently selected inside the editor text, is updated. The `SelectionRangeChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextSelectionRange>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `IsHyperlinkSelectedChanged`&mdash;Raised when a hyperlink inside the editor is selected. The `IsHyperlinkSelectedChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<bool>` provides the <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

## See Also

- [Commands]({%slug richtexteditor-commands%})
- [Configure the RichTextEditor]({%slug richtexteditor-configuration%})
- [Working with images]({%slug richtexteditor-images-overview%})
- [Hyperlinks]({%slug richtexteditor-hyperlink-support%})