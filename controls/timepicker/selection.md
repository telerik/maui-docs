---
title: Selection
page_title: .NET MAUI TimePicker Documentation | Selection
description: Check our &quot;Selection&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 5
previous_url: /controls/timepicker/timepicker-selection
slug: timepicker-selection
---

# Selection

The TimePicker control enables users to quickly and easily select a time value. This topic explains the TimePicker API related to time selection.

## Time Property

To define the current time selection, use the `Time`(`TimeSpan?`) property. The default value is `null`.

```XAML
<telerik:RadTimePicker Time="10:30:00"/>
```

Add the namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Clear Button

You can enable a Clear button which can be used to quickly remove the selected value. To enable the button, set ``IsClearButtonVisible`` property of the TimePicker:

```XAML
<telerik:RadTimePicker Time="10:30:00"
                            IsClearButtonVisible="True" />
```

## Methods

To cancel the selected time, use the `ClearSelection` method.

```XAML
<StackLayout>
	<Button Text="Clear Selection" Clicked="OnClearSelectionClicked"/>
	<telerik:RadTimePicker x:Name="timePicker"/>
</StackLayout>
```

Call `ClearSelection` inside the button `click` event to update the `Time` property to `null`.

```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.timePicker.ClearSelection();
}
```

## Events

The TimePicker exposes the `SelectionChanged` event, which is raised when the user picks a time value.

```XAML
<telerik:RadTimePicker x:Name="timePicker"
                            SelectionChanged="TimePicker_SelectionChanged"/>
```

Add the `SelectionChanged` event, where the `sender` is of type `object`, but can be cast to the `RadTimePicker` type:

```C#
private void TimePicker_SelectionChanged(object sender, EventArgs e)
{
	// implement your logic here
}
```

## See Also

- [Templates]({% slug timepicker-templates%})
- [Commands]({% slug timepicker-commands%})
