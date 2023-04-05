---
title: Selection
page_title: .NET MAUI DatePicker Documentation - Selection
description: Check our &quot;Selection&quot; documentation article for Telerik DatePicker for .NET MAUI.
position: 6
previous_url: /controls/datepicker/datepicker-selection
slug: datepicker-selection
---

# .NET MAUI DatePicker Selection

The Telerik UI for .NET MAUI DatePicker control enables the application users to quickly and easily select a date value by providing an API related to date selection.

## Setting the Current Date Selection

To define the current date selection, use the `Date`(`DateTime?`) property. By default, `Date` is `null`.

1. Define the DatePicker and set the `Date` property.

 ```XAML
<telerik:RadDatePicker Date="2020,05,15"
                            SpinnerFormat="yyy-MMM"/>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## Removing Selected Values

You can enable the removal of the selected value by rendering a **Clear** button through the `IsClearButtonVisible` property of the DatePicker:

 ```XAML
<telerik:RadDatePicker Date="2020,05,15"
                            IsClearButtonVisible="True" />
 ```

## Clearing the Selection

The DatePicker for .NET MAUI allows you to clear the selected date through its `ClearSelection` method.

1. Define the DatePicker and set the method:

 ```XAML
<StackLayout>
    <Button Text="Clear Selection" Clicked="OnClearSelectionClicked"/>
    <telerik:RadDatePicker x:Name="datePicker"/>
</StackLayout>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. Call `ClearSelection` inside the button `click` event. As a result, the `Date` property will be updated to `null`.

 ```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.datePicker.ClearSelection();
}
 ```

## Modifying the Selection

The DatePicker exposes a `SelectionChanged` event, which is raised when the user picks a date value.

1. Set the `SelectionChanged` event.

 ```XAML
<telerik:RadDatePicker SelectionChanged="RadDatePicker_SelectionChanged"/>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. Add the `SelectionChanged` event, where the `sender` is the `RadDatePicker` instance.

 ```C#
private void RadDatePicker_SelectionChanged(object sender, EventArgs e)
{
	// Implement your logic here.
}
 ```

## See Also

- [Formatting the Telerik UI for .NET MAUI DatePicker]({%slug datepicker-formatting%})
- [.NET MAUI DatePicker Templates]({%slug datepicker-templates%})
- [.NET MAUI DatePicker Styling]({%slug datepicker-styling%})
- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
