---
title: Commands
page_title: .NET MAUI TimeSpanPicker Documentation | Commands
description: Check our &quot;Commands&quot; documentation article for Telerik TimeSpanPicker for .NET MAUI.
position: 7
slug: timespanpicker-commands
---

# Commands

The Telerik UI for .NET MAUI TimeSpanPicker exposes a number of commands for programmatic manipulation of its popup rendering.

## TimeSpanPicker Commands

The TimeSpanPicker for .NET MAUI exposes the following commands, which enable you to programmatically manipulate the display of the popup and the clearing of the selected item:

* `ToggleCommand`(`ICommand`)&mdash;Allows you to show and hide the popup. Used for selecting a time interval.
* `ClearCommand`(`ICommand`)&mdash;Allows you to clear the displayed time interval.

**Example for ToggleCommand and ClearCommand**

1. Define the TimeSpanPicker.

 ```XAML
<StackLayout>
	<Button Text="Toggle Command" Command="{Binding Source={x:Reference timeSpanPicker}, Path=ToggleCommand}"/>
	<Button Text="Clear Command" Command="{Binding Source={x:Reference timeSpanPicker}, Path=ClearCommand}"/>
	<telerikInput:RadTimePicker x:Name="timeSpanPicker" />
</StackLayout>
 ```

1. Add the namespace.

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```

## PopupSelector Commands

Through the popup, users can pick a time interval. The time interval value has to be confirmed or rejected through the **OK** and **Cancel** buttons that are displayed in the popup.

The TimeSpanPicker allows you to add custom logic for the `Accept` and `Cancel` commands, which are executed when the **OK** and **Cancel** buttons, respectively, are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command which confirms the current selection of the picker and closes the popup.
* `CancelCommand`(`ICommand`)&mdash;Defines the command which rejects the current selection of the picker and closes the popup.

You can apply the `Accept` and `Cancel` commands by using the `SelectorSettings` property of TimeSpanPicker.

**Example for AcceptCommand and CancelCommand**

1. Define the TimeSpanPicker.

 ```XAML
<StackLayout>
    <telerikInput:RadTimeSpanPicker>
        <telerikInput:RadTimeSpanPicker.SelectorSettings>
            <telerikInput:PickerPopupSelectorSettings AcceptCommand="{Binding Accept}"
                                                      CancelCommand="{Binding Cancel}"/>
        </telerikInput:RadTimeSpanPicker.SelectorSettings>
            <telerikInput:RadTimeSpanPicker.BindingContext>
                <local:ViewModel/>
            </telerikInput:RadTimeSpanPicker.BindingContext>
    </telerikInput:RadTimeSpanPicker>
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

1. Add the following namespace.

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```

## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Selection]({%slug timespanpicker-selection%})
