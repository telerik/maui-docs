---
title: Events
page_title: .NET MAUI RichTextEditor Documentation - Events
description: Learn more about the exposed events in the Telerik UI for .NET MAUI RichTextEditor control.
position: 10
slug: richtexteditor-events
---

# Events

The .NET MAUI RichTextEditor emits a set of events that allow you to configure the component's behavior in response to specific user actions.

The RichTextEditor component exposes the following events:

* `OpenHyperlinkError`&mdash;Raised when users try to open invalid URLs in the editor. The `OpenHyperlinkError` event handler receives two parameters:

	* The `Sender`, which is the RichTextEditor control;
	* `OpenHyperlinkErrorEventArgs`, which provides the following properties:
		* `Error`&mdash;of type `System.Exception`; can be used to get the exact error message;
		* `Url`&mdash;of type string; defines the URL of the hyperlink;
		* `Handled`&mdash;a boolean property indicating whether the event is handled.
		
* `IsReadOnlyChanged`&mdash;Raised when read-only mode of the RichTextEditor is switched. The `IsReadOnlyChanged` event receives two parameters:

	* The `Sender`, which is the RichTextEditor control;
	* `ValueChangedEventArgs<bool>`&mdash;provides the `NewValue` and `OldValue` properties of type `bool`, indicating the `IsReadOnly` property change.
			
* `FontFamilyChanged`&mdash;Raised when the `FontFamily` property of the RichTextEditor is modified. The `FontFamilyChanged` event handler receives two parameters:
	* The `Sender`, which is the RichTextEditor control;
	* `ValueChangedEventArgs<string>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.

* `FontSizeChanged`&mdash;Raised when the `FontSize` property of the RichTextEditor is modified. The `FontSizeChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextUnit>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.
	
* `FontAttributesChanged`&mdash;Raised when the `FontAttributes`, such as bold, italic, subscript and superscript is modified. The `FontAttributesChanged` event handler receives two parameters:
	* The `Sender`, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextFontAttributes>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.
	
* `TextDecorationsChanged`&mdash;Raised when the `TextDecorations`, such as underline and strike through is modified. The `TextDecorationsChanged` event handler receives two parameters:
	* The `Sender`, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextDecorations>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.

* `TextFormattingChanged`&mdash;Raised when the `TextFormatting`, such as such as heading, paragraph or quotation is modified. The `TextFormattingChanged` event handler receives two parameters:
	* The `Sender`, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextFormatting>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.

* `HorizontalTextAlignmentChanged`&mdash;Raised when the `HorizontalTextAlignment`, such as left, right, center or justify is modified. The `HorizontalTextAlignmentChanged` event handler receives two parameters:
	* The `Sender`, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextHorizontalAlignment>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.

* `ListTypeChanged`&mdash;Raised when the `ListType`, such as numbered or bulleted list is modified. The `ListTypeChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextListType>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.

* `TextColorChanged`&mdash;Raised when the `TextColor` property of the RichTextEditor is updated. The `TextColorChanged` event handler receives two parameters:
	* The <code>Sender</code>, which is the RichTextEditor control;
	* `ValueChangedEventArgs<Color>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.

* `HighlightTextColorChanged`&mdash;Raised when the `HighlightTextColor` property of the RichTextEditor is updated. The `HighlightTextColorChanged` event handler receives two parameters:
	* The `Sender`, which is the RichTextEditor control;
	* `ValueChangedEventArgs<Color>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.
	
* `SelectionRangeChanged`&mdash;Raised when the `SelectionRange`, which defines the start and end position of the currently selected inside the editor text, is updated. The `SelectionRangeChanged` event handler receives two parameters:
	* The `Sender`, which is the RichTextEditor control;
	* `ValueChangedEventArgs<RichTextSelectionRange>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.

* `IsHyperlinkSelectedChanged`&mdash;Raised when a hyperlink inside the editor is selected. The `IsHyperlinkSelectedChanged` event handler receives two parameters:
	* The `Sender`, which is the RichTextEditor control;
	* `ValueChangedEventArgs<bool>` provides the `NewValue` and `PreviousValue` properties of type `TValue`.

## See Also

- [Commands]({%slug richtexteditor-commands%})
- [Configure the RichTextEditor]({%slug richtexteditor-configuration%})
- [Working with images]({%slug richtexteditor-images-overview%})
- [Hyperlinks]({%slug richtexteditor-hyperlink-support%})