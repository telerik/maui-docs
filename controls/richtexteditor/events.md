---
title: Events
page_title: Xamarin RichTextEditor Documentation | Events
description: Check our &quot;Events&quot; documentation article for Telerik RichTextEditor for Xamarin control.
position: 10
slug: richtexteditor-events
---

# Events

RichTextEditor component exposes the following events:

* `OpenHyperlinkError`&mdash;Raised when users try to open invalid urls in the editor. The OpenHyperlinkError event handler receives two parameters:

	* The <code>Sender</code> which is the RichTextEditor control;
	* OpenHyperlinkErrorEventArgs provides the following properties:
		* <code>Error</code> - of type System.Exception, can be used to get the exact error message;
		* <code>Url</code> - of type string, defining the url of the hyperlink;
		* <code>Handled</code> - boolean property indicating whether the event is handled.
		
* `IsReadOnlyChanged`&mdash;Raised when read-only mode of the RichTextEditor is switched. The IsReadOnlyChanged event receives two parameters:

	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;bool&gt; provides <code>NewValue</code> and <code>OldValue</code> properties of type *bool*, indicating the IsReadOnly property change.
			
* `FontFamilyChanged`&mdash;Raised when the <code>FontFamily</code> property of the RichTextEditor is modified. The FontFamilyChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;string&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `FontSizeChanged`&mdash;Raised when the <code>FontSize</code> property of the RichTextEditor is modified. The FontSizeChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;RichTextUnit&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.
	
* `FontAttributesChanged`&mdash;Raised when the <code>FontAttributes</code>, such as bold, italic, subscript and superscript is modified. The FontAttributesChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;RichTextFontAttributes&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.
	
* `TextDecorationsChanged`&mdash;Raised when the <code>TextDecorations</code>, such as underline and strikethrough is modified. The TextDecorationsChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;RichTextDecorations&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `TextFormattingChanged`&mdash;Raised when the <code>TextFormatting</code>, such as such as heading, paragraph or quotation is modified. The TextFormattingChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;RichTextFormatting&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `HorizontalTextAlignmentChanged`&mdash;Raised when the <code>HorizontalTextAlignment</code>, such as left, right, center or justify is modified. The HorizontalTextAlignmentChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;RichTextHorizontalAlignment&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `ListTypeChanged`&mdash;Raised when the <code>ListType</code>, such as numbered or bulleted list is modified. The ListTypeChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;RichTextListType&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `TextColorChanged`&mdash;Raised when the <code>TextColor</code> property of the RichTextEditor is updated. The TextColorChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;Color&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `HighlightTextColorChanged`&mdash;Raised when the <code>HighlightTextColor</code> property of the RichTextEditor is updated. The HighlightTextColorChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;Color&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.
	
* `SelectionRangeChanged`&mdash;Raised when the <code>SelectionRange</code>, which defines the start and end position of the currently selected inside the editor text, is updated. The SelectionRangeChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;RichTextSelectionRange&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

* `IsHyperlinkSelectedChanged`&mdash;Raised when a hyperlink inside the editor is selected. The IsHyperlinkSelectedChanged event handler receives two parameters:
	* The <code>Sender</code> which is the RichTextEditor control;
	* ValueChangedEventArgs&lt;bool&gt; provides <code>NewValue</code> and <code>PreviousValue</code> properties of type `TValue`.

## See Also

