---
title: Selection
page_title: .NET MAUI Time Picker Documentation | Selection
description: Check our &quot;Selection&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 5
slug: time-picker-selection
---

# Selection

**RadTimePicker** control enables the app users to quickly and easily select a time value. This topic explaines the TimePicker API related to time selection.

## Time Property

* **Time**(*TimeSpan?*): Defines the current time selection. The default value is `null`.

```XAML
<telerikInput:RadTimePicker Time="10:30:00"/>
```

And the namespace used:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## Methods

Cancel the selected time using the **ClearSelection** method.

```XAML
<StackLayout>
	<Button Text="Clear Selection" Clicked="OnClearSelectionClicked"/>
	<telerikInput:RadTimePicker x:Name="timePicker"/>
</StackLayout>
```

Call `ClearSelection` inside the button click event - as a result `Time` property will be updated to `null`.

```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.timePicker.ClearSelection();
}
```

## Events 

* **SelectionChanged** event which is raised when the user picks a time value.

```XAML
<telerikInput:RadTimePicker x:Name="timePicker" 
                            SelectionChanged="TimePicker_SelectionChanged"/>
```

Add the `SelectionChanged` event, where the `sender` is of type `object`, but can be cast to `RadTimePicker` type:

```C#
private void TimePicker_SelectionChanged(object sender, EventArgs e)
{
	// implement your logic here
}
```

## See Also

- [Templates]({% slug time-picker-templates%})
- [Commands]({% slug time-picker-commands%})