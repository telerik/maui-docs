#inputview-text-selection
* `CursorPosition` (`int`)&mdash;Specifies the starting position of the cursor. The value must be greater than or equal to `0` and less than or equal to the length of the text.

* `SelectionLength` (`int`)&mdash;Specifies the length of the text selection. It starts at the `CursorPosition`.

* `SelectionOnFocus` (`enum` of type `Telerik.Maui.SelectionOnFocus`)&mdash;Specifies the modification over the text selection when the control receives focus. The available options are:
    * (Default) `Unchanged`&mdash;the selection will not be modified.
    * `CursorAtStart`&mdash;the cursor will be moved at the start of the text.
    * `CursorAtEnd`&mdash;the cursor will be moved at the end of the text.
    * `SelectAll`&mdash;the whole text will be selected.
#end

#inputview-validation
* `IsValueValid`(`bool`)&mdash;Specifies whether the Text entered inside the control is valid. The default value is `true`.

* `ValidationErrorMessage`(`string`)&mdash;Specifies the error message which is displayed when the text entered inside the control is not valid.

* The control in `MacCatalyst` is preserving space on its right side for the error icon. If developers are not using the validation feature of the Entry, the control has an API that makes the control takes its entire space - the `ReserveSpaceForErrorView`(`bool`) property. The default value is `true`.
The image below shows the error icon that is displayed inside the reserved space:
#end

#inputview-validation-style
Use the following properties to style the error view when validation applies:

* `ValidationErrorColor` (`Color`)&mdash;Defines the custom color for the error views.
* `ValidationErrorImageStyle` (`Style` with target type `Image`)&mdash;Defines the style that applies to the error icon.
* `ValidationErrorLabelStyle` (`Style` with target type `Label`)&mdash;Defines the style that applies to the error label.
#end

#inputview-visual-states
| Visual State | Description |
| ------------- | --------------- |
| `Normal` | Applies when the control is in normal state. |
| `Focused` | Applies when the control is focused. |
| `MouseOver` | (Desktop-only) Applies when the mouse pointer is over the control. |
| `Invalid` | Applies when there is a validation and the text entered inside the control is not valid (the `IsValueValid` property is set to `false`). |
| `InvalidFocused` | Applies when the control is focused, there is validation, and the text entered inside the control is not valid (the `IsValueValid` property is set to `false`). |
| `InvalidMouseOver` | (Desktop-only) Applies when the mouse is over the control and there is a validation and the text entered inside the control is not valid (the `IsValueValid` property is set to `false`). |
| `ReadOnly` | Applies when the control is not editable (the `IsReadOnly` property is set to `false`). |
| `ReadOnlyFocused` | Applies when the control is focused and not editable (the `IsReadOnly` property is set to `false`). |
| `ReadOnlyMouseOver` | (Desktop-only) Applies when the mouse pointer is over the control, and the control is not editable (the `IsReadOnly` property is set to `false`). |
| `ReadOnlyInvalid` | Applies when the control is not editable (the `IsReadOnly` property is set to `false`), and not valid (the `IsValueValid` property is set to `false`). |
| `ReadOnlyInvalidFocused` | Applies when the control is focused, not editable (the `IsReadOnly` property is set to `false`) and not valid (the `IsValueValid` property is set to `false`). |
| `ReadOnlyInvalidMouseOver` | (Desktop-only) Applies when the mouse pointer is over the control, and the control is not editable (the `IsReadOnly` property is set to `false`), and not valid (the `IsValueValid` property is set to `false`). |
| `Disabled` | Applies when the control is disabled. |
#end

#inputview-events
* `TextChanged`&mdash;Occurs when the text is changed. The `TextChanged` event handler receives a `TextChangedEventArgs` argument containing data related to this event. The `TextChangedEventArgs` provides the following properties:
	* `NewTextValue` (`string)`&mdash;Gets the new text value.
	* `OldTextValue` (`string)`&mdash;Gets the old text value.

* `TextChanging`&mdash;Occurs when the text in the control starts to change, but before the `Text` property is updated. The `TextChanging` event handler receives a `TextChangingEventArgs` argument containing data related to this event. The `TextChangedEventArgs` provides the following properties:
    * `NewText` (`string`)&mdash;Gets the new text that is about to be entered into the input view.
    * `OldText` (`string`)&mdash;Gets the old text that is entered into the input view.
    * `Cancel` (`bool`)&mdash;Gets or sets a value that indicates whether to cancel the text changes.

* `Completed`&mdash;Occurs when the user finalizes the text.
#end

#inputview-style-clearbutton
Style the Clear button which is displayed by default when entering text in the control using the following properties:

* `ClearButtonVisibility` (`enum` of type `Microsoft.Maui.ClearButtonVisibility`)&mdash;Defines a value indicating whether the clear button (the button that clears the text when pressed) will be visible. The options are: `Never` and `WhileEditing` (default).
* `ClearButtonStyle` (`Style` with target type `RadTemplatedButton`)&mdash;Specifies the style of the clear button. Review the [TemplatedButton Visual States]({%slug templatedbutton-visual-states%}) article for more details on the available visual states.
#end

#inputview-style
* `CornerRadius` (`Microsoft.Maui.CornerRadius`)&mdash;Defines the corners radius of the border around the input control.
* `BackgroundColor` (`Microsoft.Maui.Graphics.Color`)&mdash;Defines the background color of the input control.
* `TextColor` (`Microsoft.Maui.Graphics.Color`)&mdash;Defines the text color of the input control.
* `PlaceholderColor` (`Microsoft.Maui.Graphics.Color`)&mdash;Defines the color of the placeholder text of the input control.
* `BorderBrush` (`Microsoft.Maui.Controls.Brush`)&mdash;Defines the border brush of the input control.
* `BorderThickness` (`Microsoft.Maui.Thickness`)&mdash;Defines the border thickness of the input control.
#end

#inputview-styling-font
* `FontAttributes` (`enum` of type `Microsoft.Maui.Controls.FontAttributes`)&mdash;Defines the font attributes. The available options are:
    * (Default) `None`&mdash;No font attributes are applied.
    * `Bold`&mdash;The text is displayed in bold.
    * `Italic`&mdash;The text is displayed in italic.
* `FontFamily` (`string`)&mdash;Defines the font family.
* `FontSize` (`double`)&mdash;Defines the font size.
* `FontAutoScalingEnabled` (`bool`)&mdash;Specifies whether font auto-scaling is enabled.
#end

#inputview-text-input
* `Text` (`string`)&mdash;Defines the text.
* `TextColor` (`Microsoft.Maui.Graphics`)&mdash;Defines the color of the visible text.
* `TextTransform` (`Microsoft.Maui.TextTransform`)&mdash;Defines the transformation of the text.
* `VerticalTextAlignment` (`Microsoft.Maui.TextAlignment`)&mdash;Specifies the vertical alignment of the text.
* `HorizontalTextAlignment` (`Microsoft.Maui.TextAlignment`)&mdash;Specifies the horizontal alignment of the text.
#end

#inputview-clearbutton-visibility
## Defining the Clear Button visibility

The `ClearButtonVisibility` (`Microsoft.Maui.ClearButtonVisibility`) indicates when the clear button (the button that clears the text when pressed) can be displayed. The default value is `WhileEditing`. 
If you want to hide the clear button while entering text inside the control, then set the `ClearButtonVisibility` to `Never`.
#end