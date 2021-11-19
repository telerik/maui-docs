---
title: Commands
page_title: .NET MAUI DatePicker Documentation | Commands
description: "Use the exposed commands of the Telerik UI for .NET MAUI DatePicker to programmatically manipulate the display of its popup and clear selected dates or accept or cancel the date selection."
position: 7
slug: datepicker-commands
---

# Commands

Telerik UI for .NET MAUI DatePicker exposes a number of commands for programmatic manipulation of its popup rendering.  

## DatePicker Commands

The DatePicker supports the following commands, which enable you to control the display of its popup and clear the selected date:

* `ToggleCommand`(`ICommand`)&mdash;Allows you to show or hide the popup that is used for selecting a date value.
* `ClearCommand`(`ICommand`)&mdash;Allows you to clear the displayed date.

The following example demonstrates how to set `ToggleCommand` and `ClearCommand`.

```XAML
<StackLayout>
	<Button Text="Toggle Command" Command="{Binding Source={x:Reference datePicker}, Path=ToggleCommand}"/>
	<Button Text="Clear Command" Command="{Binding Source={x:Reference datePicker}, Path=ClearCommand}"/>
	<telerikInput:RadDatePicker x:Name="datePicker" />
</StackLayout>
```

Add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## PopupSelector Commands

Through the popup users can pick a date. The date value has to be confirmed or rejected with the **OK** or **Cancel** buttons that are located on the popup.

The DatePicker allows you to add a custom logic for the `Accept` and `Cancel` commands which are executed when the **OK** or **Cancel** buttons are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command, which confirms the current selection of the picker and closes the popup.
* `CancelCommand`(`ICommand`)&mdash;Defines the command, which rejects the current selection of the picker and closes the popup.

You can apply the `Accept` and `Cancel` commands can by using the `SelectorSettings` property of DatePicker as demonstrated in the following example.

```XAML
<StackLayout>
    <telerikInput:RadDatePicker>
        <telerikInput:RadDatePicker.SelectorSettings>
            <telerikInput:PickerPopupSelectorSettings AcceptCommand="{Binding Accept}"
                                                      CancelCommand="{Binding Cancel}"/>
        </telerikInput:RadDatePicker.SelectorSettings>
            <telerikInput:RadDatePicker.BindingContext>
                <local:ViewModel/>
            </telerikInput:RadDatePicker.BindingContext>
    </telerikInput:RadDatePicker>
</StackLayout>
```

Set the `ViewModel`.

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

Add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Formatting]({%slug datepicker-formatting%})
- [Templates]({%slug datepicker-templates%})
- [Selection]({%slug datepicker-selection%})
