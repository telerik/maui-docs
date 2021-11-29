---
title: Commands
page_title: .NET MAUI TemplatedPicker Documentation | Commands
description: Check our &quot;Commands&quot; documentation article for Telerik TemplatedPicker for .NET MAUI.
position: 7
slug: templatedpicker-commands
---

# Commands

Telerik UI for .NET MAUI TemplatedPicker exposes a number of commands for programmatic manipulation of its popup rendering.

## TemplatedPicker Commands

The TemplatedPicker for .NET MAUI exposes the following commands, which enable you to programmatically manipulate the display of the popup and the clearing of the selected item:

* `ToggleCommand`&mdash;Allows you to show/hide the popup. Used for selecting an item from the custom picker.
* `ClearCommand`&mdash;Allows you to clear the displayed item.

## PopupSelector Commands

Through the popup, users can pick an item. The value has to be confirmed or rejected through the **OK** and **Cancel** buttons that are displayed in the popup.

The TemplatedPicker allows you to add custom logic for the `Accept` and `Cancel` commands, which are executed when the **OK** and **Cancel** buttons, respectively, are clicked.

* `AcceptCommand`&mdash;Defines the command which confirms the current selection of the picker and closes the popup.
* `CancelCommand`&mdash;Defines the command which rejects the current selection of the picker and closes the popup.

You can apply the `Accept` and `Cancel` commands by using the `SelectorSettings` property of TemplatedPicker.

## Example

1. Define the TemplatedPicker:

 ```XAML
<StackLayout>
    <Button Text="Toggle Command" Command="{Binding Source={x:Reference picker}, Path=ToggleCommand}"/>
    <Button Text="Clear Command" Command="{Binding Source={x:Reference picker}, Path=ClearCommand}"/>
    <telerikInput:RadTemplatedPicker x:Name="picker">
        <telerikInput:RadTemplatedPicker.SelectorTemplate>
            <ControlTemplate>
                <telerikInput:RadCalendar SelectedDate="{TemplateBinding SelectedValue, Mode=TwoWay}"/>
            </ControlTemplate>
        </telerikInput:RadTemplatedPicker.SelectorTemplate>
		<telerikInput:RadTemplatedPicker.SelectorSettings>
                <telerikInput:PickerPopupSelectorSettings AcceptCommand="{Binding Accept}"
                                                          CancelCommand="{Binding Cancel}"/>
            </telerikInput:RadTemplatedPicker.SelectorSettings>
            <telerikInput:RadTemplatedPicker.BindingContext>
                <local:ViewModel/>
            </telerikInput:RadTemplatedPicker.BindingContext>
    </telerikInput:RadTemplatedPicker>
</StackLayout>
 ```

1. Set a sample `ViewModel`:

 ```C#
public class ViewModel
{
    public ViewModel()
    {
        this.Accept = new Command(this.OnAccept);
        this.Accept = new Command(this.OnCancel);
    }

    private void OnAccept(object obj)
    {
        // implement your custom logic here
    }

    private void OnCancel(object obj)
    {
        // implement your custom logic here
    }

    public ICommand Accept { get; set; }
    public ICommand Cancel { get; set; }
}
 ```

1. Set the defined `ViewModel` as a `BindingContext` of the page:

 ```C#
this.BindingContext = new ViewModel();
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```



## See Also

- [Events]({%slug templatedpicker-events%})
- [Templates]({%slug templatedpicker-templates%})
