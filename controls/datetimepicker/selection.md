---
title: Selection
page_title: .NET MAUI DateTimePicker Documentation | Selection
description: Check our &quot;Selection&quot; documentation article for Telerik DateTimePicker for .NET MAUI.
position: 5
slug: datetimepicker-selection
---

# Selection

The DateTimePicker control enables the application users to quickly and easily select a date value by providing an API related to date selection.

## Date Property

The `Date`(`DateTime?`) property defines the current date selection. Its default value is `null`.

The following example demonstrates how to set the `Date` property.

```XAML
<telerikInput:RadDateTimePicker Date="2020,05,15"
                            SpinnerFormat="yyy-MMM"/>
```

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## Clear Button

You can enable a Clear button which can be used to quickly remove the selected value. To enable the button, set `IsClearButtonVisible` property of the DateTimePicker:

```XAML
<telerikInput:RadDateTimePicker Date="2020,05,15"
                            IsClearButtonVisible="True" />
```

## Methods

The DateTimePicker for .NET MAUI allows you to clear the selected date through its `ClearSelection` method:

```XAML
<StackLayout>
    <Button Text="Clear Selection" Clicked="OnClearSelectionClicked"/>
    <telerikInput:RadDateTimePicker x:Name="dateTimePicker"/>
</StackLayout>
```

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

Call `ClearSelection` inside the button `click` event. As a result, the `Date` property will be updated to `null`.

```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.dateTimePicker.ClearSelection();
}
```

## Events

The DateTimePicker exposes a `SelectionChanged` event, which is raised when the user picks a date value.

The following example demonstrates how to use `SelectionChanged`.

```XAML
<telerikInput:RadDateTimePicker SelectionChanged="RadDateTimePicker_SelectionChanged"/>
```

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

Add the `SelectionChanged` event, where the `sender` is the `RadDateTimePicker` instance.

```C#
private void RadDateTimePicker_SelectionChanged(object sender, EventArgs e)
{
	// implement your logic here
}
```

## See Also

- [Default Dates]({%slug datetimepicker-default-dates%})
- [Commands]({% slug datetimepicker-commands%})
- [Templates]({% slug datetimepicker-templates%})
