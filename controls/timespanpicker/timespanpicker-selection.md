---
title: Selection
page_title: .NET MAUI TimeSpanPicker Documentation | Selection
description: Check our &quot;Selection&quot; documentation article for Telerik TimeSpanPicker for .NET MAUI.
position: 6
slug: timespanpicker-selection
---

# Selection

**RadTimeSpanPicker** control enables the app users to quickly and easily select a time interval. This topic explaines the TimeSpanPicker API related to time interval selection.

## Time Property

* `Time`(*TimeSpan?*): Defines the current selection of time interval. The default value is null.

### Example 

```XAML
<telerikInput:RadTimeSpanPicker Time="5:10:30:00"/>
```

And the namespace used:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## Methods

Cancel the selected time using the `ClearSelection` method.

### Example

```XAML
<StackLayout>
    <Button Text="Clear Selection" Clicked="OnClearSelectionClicked"/>
    <telerikInput:RadTimeSpanPicker x:Name="timeSpanPicker"/>
</StackLayout>
```

And the namespace used:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

Call ClearSelection inside the button click event - as a result Time property will be updated to null.

```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.timeSpanPicker.ClearSelection();
}
```

## Events

* `SelectionChanged` event which is raised when the user picks a time value.

### Example

```XAML
<telerikInput:RadTimeSpanPicker SelectionChanged="RadTimeSpanPicker_SelectionChanged"/>
```

And the namespace used:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

and the `SelectionChanged` event, where the `sender` is the `RadTimeSpanPicker` control

```C#
private void RadTimeSpanPicker_SelectionChanged(object sender, EventArgs e)
{
	// implement your logic here
}
```

## See Also

- [Templates]({% slug timespanpicker-templates%})
- [Commands]({% slug timespanpicker-commands%})