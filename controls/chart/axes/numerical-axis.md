---
title: Numerical Axis
page_title: .NET MAUI Chart Documentation - Numerical Axis
slug: axes-numerical-axis
description: Check our &quot;Numerical Axis&quot; documentation article for Telerik Chart for .NET MAUI.
position: 3
previous_url: /controls/chart/axes/axes-numerical-axis
---

# .NET MAUI Chart Numerical Axis

The Numerical Axis plots the associated data points by using each point's numerical value, provided for the axis. It will build a numerical range (user-defined or automatically calculated) and will determine each data point X or Y coordinate (depending on whether the axis is specified as `Horizontal` or as `Vertical`).

The axis works with either categorical or scatter data. For categorical data, the axis uses the `ValueBinding` property of the data points, while for scatter data, the axis uses the `XValueBinding` or the `YValueBinding` property depending on whether the axis is horizontal or vertical.

The `NumericalAxis` inherits from the base `Axis` class. For more information, refer to the article on [inherited properties]({% slug axes-overview %}).

## Features

The Numerical Axis exposes the following properties:

- `LabelFormat`&mdash;Provides a format string that will be used when converting the label value to a string. For example, any numeric format like `"N"`, `"P2"`.
- `Minimum`&mdash;Defines the minimum value of the axis. By default, the axis itself will calculate the minimum, depending on the minimum value of the plotted data points.
- `Maximum`&mdash;Defines the maximum value of the axis. By default, the axis itself will calculate the maximum, depending on the maximum value of the plotted data points.
- `RangeExtendDirection`&mdash;Defines a value that specifies how the actual range of the axis (when auto-calculated) will be extended. By default the axis will calculate its minimum and maximum values in such a way that the data is best visualized. For example, if the maximum data point value is `50`, the axis will make its maximum value `50` plus the `MajorStep`, so that the plotted data will not intersect with the top of the plot area. The available values are:
	- `None`
	- `Positive`
	- `Negative`
	- Both
- `MajorStep`&mdash;Specifies the step at which the major ticks are positioned on the axis. If this property is set to `0`, the axis will automatically calculate the step so that the data will be visualized in the best possible way.

## Example

Define the Numerical Axis:

```XAML
<telerik:NumericalAxis LabelFormat="C"
					   MajorStep="0.5"
					   Minimum="-1"
					   Maximum="1" />
```

## See Also

- [Axis Overview]({%slug axes-overview%})
- [Categorical Axis]({%slug axes-categorical-axis%})
- [DateTimeContinuous Axis]({%slug axes-date-time-continuous-axis%})
