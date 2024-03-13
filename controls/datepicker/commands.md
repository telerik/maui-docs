---
title: Commands
page_title: .NET MAUI DatePicker Documentation - Commands
description: Use the exposed commands of the Telerik UI for .NET MAUI DatePicker to programmatically manipulate the display of its popup and clear selected dates or accept or cancel the date selection.
position: 8
previous_url: /controls/datepicker/datepicker-commands
slug: datepicker-commands
---

# .NET MAUI DatePicker Commands

Telerik UI for .NET MAUI DatePicker exposes a number of commands for programmatic manipulation of its popup rendering.  

## DatePicker Commands

The DatePicker supports the following commands, which enable you to control the display of its popup and clear the selected date:

* `ToggleCommand`(`ICommand`)&mdash;Allows you to show or hide the popup that is used for selecting a date value.
* `ClearCommand`(`ICommand`)&mdash;Allows you to clear the displayed date.

The following example demonstrates how to set the `ToggleCommand` and `ClearCommand`.

**1.** Set `ToggleCommand` and `ClearCommand`.

```XAML
<StackLayout>
	<Button Text="Toggle Command" Command="{Binding Source={x:Reference datePicker}, Path=ToggleCommand}"/>
	<Button Text="Clear Command" Command="{Binding Source={x:Reference datePicker}, Path=ClearCommand}"/>
	<telerik:RadDatePicker x:Name="datePicker" />
</StackLayout>
```

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## OK and Cancel Buttons

Through the popup or the drop-down, users can pick a date. The date value must be confirmed or rejected with the **OK** or **Cancel** buttons located in the popup or drop-down.

The DatePicker allows you to add a custom logic for the `Accept` and `Cancel` commands which are executed when the **OK** or **Cancel** buttons are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command, which confirms the current selection of the picker and closes the popup or drop-down. Use `AcceptCommandParameter` to pass a parameter to the command execute method. 
* `CancelCommand`(`ICommand`)&mdash;Defines the command, which rejects the current selection of the picker and closes the popup or drop-down. Use `CancelCommandParameter` to pass a parameter to the command execute method.

You can apply the `Accept` and `Cancel` commands for the popup mode by setting the `PopupSettings` property of the DatePicker. For the drop-down mode, use the `DropDownSettings` property.

**1.** Define the control and add the commands.

```XAML
<VerticalStackLayout>
    <telerik:RadDatePicker x:Name="datePicker"> 
        <telerik:RadDatePicker.PopupSettings>
            <telerik:PickerPopupSettings AcceptCommand="{Binding Accept}"
                                         AcceptCommandParameter="{Binding Date, Source={x:Reference datePicker}}"
										 CancelCommand="{Binding Cancel}"
										 CancelCommandParameter="{Binding Date, Source={x:Reference datePicker}}"/>
        </telerik:RadDatePicker.PopupSettings>
            <telerik:RadDatePicker.BindingContext>
                <local:ViewModel/>
            </telerik:RadDatePicker.BindingContext>
    </telerik:RadDatePicker>
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

- [Formatting the Telerik UI for .NET MAUI DatePicker]({%slug datepicker-formatting%})
- [Setting Date Ranges in the .NET MAUI DatePicker]({%slug datepicker-date-range%})
- [.NET MAUI DatePicker Templates]({%slug datepicker-templates%})
- [.NET MAUI DatePicker Selection]({%slug datepicker-selection%})
- [.NET MAUI DatePicker Styling]({%slug datepicker-styling%})
- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
