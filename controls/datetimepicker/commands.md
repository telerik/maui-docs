---
title: Commands
page_title: .NET MAUI DateTimePicker Documentation - Commands
description: Use the exposed commands of the Telerik UI for .NET MAUI DateTimePicker to programmatically manipulate the display of its popup and clear selected dates or accept or cancel the date selection.
position: 7
slug: datetimepicker-commands
---

# .NET MAUI DateTimePicker Commands

Telerik UI for .NET MAUI DateTimePicker exposes a number of commands for programmatic manipulation of its popup rendering.  

## DateTimePicker Commands

The DateTimePicker supports the following commands, which enable you to control the display of its popup and clear the selected date:

* `ToggleCommand`(`ICommand`)&mdash;Allows you to show or hide the popup that is used for selecting a date value.
* `ClearCommand`(`ICommand`)&mdash;Allows you to clear the displayed date.

The following example demonstrates how to set `ToggleCommand` and `ClearCommand`.

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

## Settings Commands

Through the popup or the drop-down, users can pick a date and time. The date and time value must be confirmed or rejected with the **OK** or **Cancel** buttons located in the popup/drop-down.

The DateTimePicker allows you to add a custom logic for the `Accept` and `Cancel` commands which are executed when the **OK** or **Cancel** buttons are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command, which confirms the current selection of the picker and closes the popup/drop-down.
* `CancelCommand`(`ICommand`)&mdash;Defines the command, which rejects the current selection of the picker and closes the popup/drop-down.

You can apply the `Accept` and `Cancel` commands for popup mode by setting the `PopupSettings` and for drop-down mode by setting `DropDownSettings` property of DateTimePicker.

**1.** Define the control and add the commands to the `PopupSettings`.

 ```XAML
<StackLayout>
    <telerik:RadDateTimePicker>
        <telerik:RadDateTimePicker.PopupSettings>
            <telerik:PickerPopupSettings AcceptCommand="{Binding Accept}"
                                         CancelCommand="{Binding Cancel}"/>
        </telerik:RadDateTimePicker.PopupSettings>
            <telerik:RadDateTimePicker.BindingContext>
                <local:ViewModel/>
            </telerikInput:RadDateTimePicker.BindingContext>
    </telerik:RadDateTimePicker>
</StackLayout>
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

**3.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [Formatting]({%slug datetimepicker-formatting%})
- [Templates]({%slug datetimepicker-templates%})
- [Selection]({%slug datetimepicker-selection%})
