---
title: Selection
page_title: .NET MAUI TimeSpanPicker Documentation - Selection
description: Check our &quot;Selection&quot; documentation article for Telerik TimeSpanPicker for .NET MAUI.
position: 6
previous_url: /controls/timespanpicker/timespanpicker-selection
slug: timespanpicker-selection
---

# .NET MAUI TimeSpanPicker Selection

The TimeSpanPicker control enables users to quickly and easily select a time interval. This topic explains the TimeSpanPicker API related to the time-interval selection.

## Time Property

To define the current time-interval selection, use the `Time`(`TimeSpan?`) property. The default value is `null`.

The following example shows how to set the `Time` property.

Define the TimeSpanPicker.

```XAML
<telerik:RadTimeSpanPicker Time="5:10:30:00"/>
```

Add the namespace.

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Clear Button

You can enable a Clear button which can be used to quickly remove the selected value. To enable the button, set ``IsClearButtonVisible`` property of the TimePicker:

```XAML
<telerik:RadTimeSpanPicker Time="5:10:30:00"
								IsClearButtonVisible="True" />
```

## Methods

To cancel the selected time, use the `ClearSelection` method.

The following example shows how to set the `ClearSelection` method.

1. Define the TimeSpanPicker.

 ```XAML
<StackLayout>
    <Button Text="Clear Selection" Clicked="OnClearSelectionClicked"/>
    <telerik:RadTimeSpanPicker x:Name="timeSpanPicker"/>
</StackLayout>
 ```

1. Add the namespace.

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. Call `ClearSelection` inside the button `click` event. As a result, the `Time` property will be updated to `null`.

 ```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.timeSpanPicker.ClearSelection();
}
 ```


## Events

The TimeSpanPicker exposes the `SelectionChanged` event, which is raised when the user picks a time value.

The following example shows how to set the `SelectionChanged` event.

1. Define the TimeSpanPicker.

 ```XAML
<telerik:RadTimeSpanPicker SelectionChanged="RadTimeSpanPicker_SelectionChanged"/>
 ```

1. Add the namespace.

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. Define the `SelectionChanged` event where the `sender` is the `RadTimeSpanPicker` control.

 ```C#
private void RadTimeSpanPicker_SelectionChanged(object sender, EventArgs e)
{
	// implement your logic here
}
 ```

## See Also

- [Templates]({% slug timespanpicker-templates%})
- [Commands]({% slug timespanpicker-commands%})
