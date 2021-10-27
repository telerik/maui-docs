---
title: Selection
page_title: .NET MAUI DatePicker Documentation | Selection
description: Check our &quot;Selection&quot; documentation article for Telerik DatePicker for .NET MAUI.
position: 5
slug: datepicker-selection
---

# Selection

RadDatePicker control enables the app users to quickly and easily select a date value. This topic will go through the provided by the DatePicker API related to date selection.

## Important Properties

* `Date`(*DateTime?*): Defines the current date selection. The default value is null.

Check below a quick example of Time property usage:

<snippet id='datepicker-keyfeatures-date-spinnerformat' />
```XAML
<telerikInput:RadDatePicker Date="2020,05,15"
                            SpinnerFormat="yyy-MMM"/>
```

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## Methods

DatePicker for .NET MAUI allows you to clear the selected date through its `ClearSelection` method:

```XAML
<StackLayout>
    <Button Text="Clear Selection" Clicked="OnClearSelectionClicked"/>
    <telerikInput:RadDatePicker x:Name="datePicker"/>
</StackLayout>
```

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

Call `ClearSelection` inside the button click event - as a result Date property will be updated to null.

```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.datePicker.ClearSelection();
}
```

## Events

RadDatePicker exposes a `SelectionChanged` event which is raised when the user picks a date value.

### Example

```XAML
<telerikInput:RadDatePicker SelectionChanged="RadDatePicker_SelectionChanged"/>
```

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

and the `SelectionChanged` event, where the *sender* is the RadDatePicker instance:

```C#
private void RadDatePicker_SelectionChanged(object sender, EventArgs e)
{
	// implement your logic here
}
```

## See Also

- [Default Dates]({%slug datepicker-default-dates%})
- [Commands]({% slug datepicker-commands%})
- [Templates]({% slug datepicker-templates%})
