---
title: Overview
page_title: .NET MAUI Chart Documentation | Axes Overview
position: 1
description: Check our &quot;Overview&quot; documentation article for Telerik Chart for .NET MAU
slug: axes-overview
---

# Overview

The Cartesian Chart plots data points in a coordinate system defined by its two axes. Instead of having one axis type that does hundreds of things, axes provides a hierarchy where each concrete axis type exposes a specific functionality.

![Axes Class Diagram](images/axes-class-diagram.png)

The predefined axis types are:

- [Numerical Axis]({%slug axes-numerical-axis%})
- [Categorical Axis]({%slug axes-categorical-axis%})
- [Date-Time Continuous Axis]({%slug axes-date-time-continuous-axis%})

## Common Axis Features

The common axis functionality is encapsulated by the abstract `Axis` class and is responsible for displaying ticks that simply mark values on the axis at fixed positions. The axis also displays labels that are used to provide a visualization of the values at some or all of the ticks. The default visualization of the labels is text, and the default visuals created internally are text blocks.

The following sections list all the properties exposed by the base axis type.

### Label Style and Position

You can customize the labels orientation and style with the following properties:

- `LabelFitMode`&mdash;Specifies how labels that exceed the axis bounding rectangle will be positioned. The available fit options are:
 - `MultiLine`&mdash;Arranges axis labels on multiple lines with each label located on a line different from its neighbor labels.
 - `Rotate`&mdash;Arranges the axis labels so that they are rotated some degrees around their top left corner.
- `LabelFontSize`&mdash;Specifies the font size of the labels.
- `LabelTextColor`&mdash;Specifies the color of the labels.

#### Example

```XAML
<telerikChart:CategoricalAxis LabelFitMode="Rotate"
							  LabelFontSize="25"
							  LabelTextColor="#FFCC88CC"/>
```

### Label Format

You can customize the labels text with the following properties:

- `LabelFormat`&mdash;Provides a format string that will be used when converting the label value to a string. Each axis type requires different format:
  - `NumericalAxis`&mdash;Aany numeric format like `"N"`, `"P2"`.
  - `DateTimeContinuousAxis`&mdash;Any date format like `"dd-MM-yy"`, `"HH:mm"`.
  - `CategoricalAxis`&mdash;`"{0} items"`, `"{0:N}"`.
- `LabelFormatter`&mdash;Specifies a custom formatter that implements the `ILabelFormatter` interface to apply a custom rule for setting each label text.

#### Example

The following example shows how to set `LabelFormat` to a Numerical Axis:

```XAML
<telerikChart:NumericalAxis LabelFormat="C"
							MajorStep="0.5"
							Minimum="-1"
							Maximum="1" />
```

### Label Formatter

The `LabelFormatterBase<T>` class is a base implementation of the `ILabelFormatter` interface that can be used in the most common scenarios.

#### Example

The following example shows how to set a label formatter for the Date-Time Continuous Axis.

<snippet id='chart-customization-format-axis-labels-label-formatter'/>

You can apply it in the following way:

```XAML
<telerikChart:DateTimeContinuousAxis LabelFitMode="Rotate"
                                     MajorStepUnit="Day">
    <telerikChart:DateTimeContinuousAxis.LabelFormatter>
        <local:DateLabelFormatter />
    </telerikChart:DateTimeContinuousAxis.LabelFormatter>
</telerikChart:DateTimeContinuousAxis>
```

### Styling the Axis Line and Ticks

You can customize the appearance of the axis line and ticks with the following properties:

- `MajorTickBackgroundColor`&mdash;Specifies the major ticks color.
- `MajorTickThickness`&mdash;Specifies the thickness of the major ticks.
- `LineColor`&mdash;Specifies the color of the axis line.
- `LineDashArray`&mdash;Specifies the array that is used to create a dash line, which will be applied to the axis line.

#### Example

```XAML
	<telerikChart:NumericalAxis MajorTickBackgroundColor="#FFCC88CC"
								MajorTickThickness="5"
								LineColor="#FFCC88CC"/>
```

### Location

You can specify the location of the axis with the following properties:

- `HorizontalLocation`&mdash;Specifies the horizontal location of the axis. Applicable for vertical axes.
- `VerticalLocation`&mdash;Specifies the vertical location of the axis. Applicable for horizontal axes.

#### Example

```XAML
	<telerikChart:CategoricalAxis VerticalLocation="Top"/>
```

## See Also

- [Categorical Axis]({%slug axes-categorical-axis%})
- [Numerical Axis]({%slug axes-numerical-axis%})
- [DateTimeContinuous Axis]({%slug axes-date-time-continuous-axis%})
