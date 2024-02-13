---
title: Commands
page_title: .NET MAUI DateTimePicker Documentation - Commands
description: Use the exposed commands of the Telerik UI for .NET MAUI DateTimePicker to programmatically manipulate the display of its popup and clear selected dates or accept or cancel the date selection.
position: 7
slug: datetimepicker-commands
control_name: DateTimePicker
---

# .NET MAUI DateTimePicker Commands

Telerik UI for .NET MAUI DateTimePicker exposes a number of commands for programmatic manipulation of its popup rendering.  

## DateTimePicker Commands

The DateTimePicker supports the following commands, which enable you to control the display of its popup and clear the selected date:

* `ToggleCommand`(`ICommand`)&mdash;Allows you to show or hide the popup that is used for selecting a date value.
* `ClearCommand`(`ICommand`)&mdash;Allows you to clear the displayed date.

The following example demonstrates how to set the `ToggleCommand` and `ClearCommand`.

**1.** Define the `RadDateTimePicker` and add two buttons for command binding:

```XAML
<VerticalStackLayout>
	<Button Text="Toggle Command" Command="{Binding Source={x:Reference dateTimePicker}, Path=ToggleCommand}"/>
	<Button Text="Clear Command" Command="{Binding Source={x:Reference dateTimePicker}, Path=ClearCommand}"/>
	<telerik:RadDateTimePicker x:Name="dateTimePicker" />
</VerticalStackLayout>
```

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## OK and Cancel Buttons

{% include ok-cancel-buttons.md %}

**1.** Define the control and add the commands to the `PopupSettings`.

```XAML
<VerticalStackLayout>
    <telerik:RadDateTimePicker x:Name="dateTimePicker"> 
        <telerik:RadDateTimePicker.PopupSettings>
            <telerik:PickerPopupSettings AcceptCommand="{Binding Accept}"
                                         AcceptCommandParameter="{Binding Date, Source={x:Reference dateTimePicker}}"
										 CancelCommand="{Binding Cancel}"
										 CancelCommandParameter="{Binding Date, Source={x:Reference dateTimePicker}}"/>
        </telerik:RadDateTimePicker.PopupSettings>
            <telerik:RadDateTimePicker.BindingContext>
                <local:ViewModel/>
            </telerik:RadDateTimePicker.BindingContext>
    </telerik:RadDateTimePicker>
</VerticalStackLayout>
```

**2.** Set the `ViewModel`.

```C#
public class ViewModel
{
    public ICommand Accept { get; set; }
    public ICommand Cancel { get; set; }

    public ViewModel()
    {
        this.Accept = new Command(this.OnAccept);
        this.Cancel = new Command(this.OnCancel);
    }

    private void OnAccept(object param)
    {
        Application.Current.MainPage.DisplayAlert("Date selected", String.Format("New Date: {0:d}", (DateTime)param), "OK");
        // implement your custom logic here
    }

    private void OnCancel(object param)
    {
        var message = param != null ? String.Format("Current date: {0:d}", (DateTime)param) : "Currently no date is selected";
        Application.Current.MainPage.DisplayAlert("Date Selection Canceled", message, "OK");
        // implement your custom logic here
    }
}
```

**3.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [Formatting]({%slug datetimepicker-formatting%})
- [Templates]({%slug datetimepicker-templates%})
- [Selection]({%slug datetimepicker-selection%})
