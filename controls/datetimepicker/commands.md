---
title: Commands
page_title: .NET MAUI DateTimePicker Documentation | Commands
description: "Use the exposed commands of the Telerik UI for .NET MAUI DateTimePicker to programmatically manipulate the display of its popup and clear selected dates or accept or cancel the date selection."
position: 7
slug: datetimepicker-commands
---

# Commands

Telerik UI for .NET MAUI DateTimePicker exposes a number of commands for programmatic manipulation of its popup rendering.  

## DateTimePicker Commands

The DateTimePicker supports the following commands, which enable you to control the display of its popup and clear the selected date:

* `ToggleCommand`(`ICommand`)&mdash;Allows you to show or hide the popup that is used for selecting a date value.
* `ClearCommand`(`ICommand`)&mdash;Allows you to clear the displayed date.

The following example demonstrates how to set `ToggleCommand` and `ClearCommand`.

```XAML
<VerticalStackLayout>
	<Button Text="Toggle Command" Command="{Binding Source={x:Reference dateTimePicker}, Path=ToggleCommand}"/>
	<Button Text="Clear Command" Command="{Binding Source={x:Reference dateTimePicker}, Path=ClearCommand}"/>
	<telerik:RadDateTimePicker x:Name="dateTimePicker" />
</VerticalStackLayout>
```

Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## PopupSelector Commands

Through the popup users can pick a date. The date value has to be confirmed or rejected with the **OK** or **Cancel** buttons that are located on the popup.

The DateTimePicker allows you to add a custom logic for the `Accept` and `Cancel` commands which are executed when the **OK** or **Cancel** buttons are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command, which confirms the current selection of the picker and closes the popup.
* `CancelCommand`(`ICommand`)&mdash;Defines the command, which rejects the current selection of the picker and closes the popup.

You can apply the `Accept` and `Cancel` commands can by using the `SelectorSettings` property of DateTimePicker.

1. Define the control and add the commands.

 ```XAML
<StackLayout>
    <telerik:RadDateTimePicker>
        <telerik:RadDateTimePicker.SelectorSettings>
            <telerik:PickerPopupSelectorSettings AcceptCommand="{Binding Accept}"
                                                      CancelCommand="{Binding Cancel}"/>
        </telerik:RadDateTimePicker.SelectorSettings>
            <telerik:RadDateTimePicker.BindingContext>
                <local:ViewModel/>
            </telerikInput:RadDateTimePicker.BindingContext>
    </telerik:RadDateTimePicker>
</StackLayout>
 ```

1. Set the `ViewModel`.

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

    private void OnAccept(object obj)
    {
        // implement your custom logic here
    }

    private void OnCancel(object obj)
    {
        // implement your custom logic here
    }
}
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## See Also

- [Formatting]({%slug datetimepicker-formatting%})
- [Templates]({%slug datetimepicker-templates%})
- [Selection]({%slug datetimepicker-selection%})
