---
title: Selection
page_title: .NET MAUI TimeSpanPicker Documentation | Selection
description: Check our &quot;Selection&quot; documentation article for Telerik TimeSpanPicker for .NET MAUI.
position: 6
slug: timespanpicker-selection
---

# Selection

The TimeSpanPicker control enables users to quickly and easily select a time interval. This topic explains the TimeSpanPicker API related to the time-interval selection.

## Time Property

To define the current time-interval selection, use the `Time`(`TimeSpan?`) property. The default value is `null`.

The following example shows how to set the `Time` property.

Define the TimeSpanPicker.

```XAML
<telerikInput:RadTimeSpanPicker Time="5:10:30:00"/>
```

Add the namespace.

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```


## Methods

To cancel the selected time, use the `ClearSelection` method.

The following example shows how to set the `ClearSelection` method.

1. Define the TimeSpanPicker.

 ```XAML
<StackLayout>
    <Button Text="Clear Selection" Clicked="OnClearSelectionClicked"/>
    <telerikInput:RadTimeSpanPicker x:Name="timeSpanPicker"/>
</StackLayout>
 ```

1. Add the namespace.

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
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
<telerikInput:RadTimeSpanPicker SelectionChanged="RadTimeSpanPicker_SelectionChanged"/>
 ```

1. Add the namespace.

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
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
