#charts-tooltip-display-position-format
## Display the Tooltip

To open the tooltip, set the `TriggerMode` (`enum` of type `Telerik.Maui.Controls.Charts.ChartTooltipTriggerMode`) property of the `ChartTooltipBehavior`. The available options are:
* `Tap`&mdash;The tooltip opens when you tap a data point. Default on mobile platforms.
* `Hover`&mdash;The tooltip opens when you hover over a data point. Default on desktop platforms.
* `Hold`&mdash;The tooltip opens when you press and hold a data point.

To define a delay before the tooltip is shown or hidden, use the following properties of the `ChartTooltipBehavior`:

* `HoverDelay` (`int`)&mdash;Defines the delay in milliseconds before the tooltip is shown. Applies only to the `Hover` trigger mode and only to the initial show. The default value is `0`.
* `HideDelay` (`int`)&mdash;Defines the delay in milliseconds before the tooltip is hidden. For the `Hold` trigger mode, the delay starts when the press is released. This property has no effect for the `Hover` trigger mode.

## Position the Tooltip

To position the tooltip, use the `PlacementMode` (`enum` of type `Telerik.Maui.Controls.Charts.ChartTooltipPlacementMode`) property. The available options are:
* `Pointer` (default)&mdash;Places the tooltip at the pointer or tap position.
* `DataPoint`&mdash;Places the tooltip at a fixed position relative to the data point.


## Format the Tooltip Label

To format the value displayed in the tooltip, use the `TooltipLabelFormat` (`string`) property of the `ChartTooltipBehavior`. The format string is applied to the value of the data point. For example, to display a percentage with two decimal places, set the `TooltipLabelFormat` to `"{0:P2}"`.
#end

#charts-tooltip-style
Use the `TooltipStyle` property of the `ChartTooltipBehavior` to apply a `Style` with target type `ChartTooltip`. Set the following properties to style the tooltip's appearance:

* `TextColor` (`Color`)&mdash;Defines the color of the tooltip text.
* `FontSize` (`double`)&mdash;Defines the font size of the tooltip text.
* `FontFamily` (`string`)&mdash;Defines the font family of the tooltip text.
* `FontAttributes` (`FontAttributes`)&mdash;Defines the font attributes of the tooltip text.
* `BackgroundColor` (`Color`)&mdash;Defines the background color of the tooltip.
* Border properties (`BorderColor`, `BorderBrush` `BorderThickness`, `CornerRadius`)&mdash;Define the border of the tooltip.
* `ContentPadding` (`Thickness`)&mdash;Defines the padding of the tooltip content.
#end

