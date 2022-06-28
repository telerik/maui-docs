---
title: Commands
page_title: .NET MAUI TimePicker Documentation - Commands
description: Check our &quot;Commands&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 7
previous_url: /controls/timepicker/timepicker-commands
slug: timepicker-commands
---

# Commands

The Telerik UI for .NET MAUI TimePicker exposes a number of commands for programmatic manipulation of its popup rendering.

## TimePicker Commands

The TimePicker for .NET MAUI exposes the following commands, which enable you to programmatically manipulate the display of the popup and the clearing of the selected item:

* `ToggleCommand`(`ICommand`)&mdash;Allows you to show and hide the popup. Used for selecting a time value.
* `ClearCommand`(`ICommand`)&mdash;Allows you to clear the selected time.

The following example shows how to set the `ToggleCommand` and `ClearCommand`.

1. Define the TimePicker.

 ```XAML
<StackLayout>
	 <Button Text="Toggle Popup" Command="{Binding Source={x:Reference timePicker}, Path=ToggleCommand}"/>
     <Button Text="Clear Selected Time" Command="{Binding Source={x:Reference timePicker}, Path=ClearCommand}"/>
	<telerik:RadTimePicker x:Name="timePicker" />
</StackLayout>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## PopupSelector Commands

Through the popup, users can pick a time. The value has to be confirmed or rejected through the **OK** and **Cancel** buttons that are displayed in the popup.

The TimePicker allows you to add custom logic for the `Accept` and `Cancel` commands, which are executed when the **OK** and **Cancel** buttons, respectively, are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command which confirms the current selection of the picker and closes the popup.
* `CancelCommand`(`ICommand`)&mdash;Defines the command which rejects the current selection of the picker and closes the popup.

You can apply the `Accept` and `Cancel` commands by using the `SelectorSettings` property of TemplatedPicker.

The following example shows how to set the `AcceptCommand` and `CancelCommand`.

1. Define the TimePicker.

 ```XAML
<telerik:RadTimePicker x:Name="timePicker">
	<telerik:RadTimePicker.SelectorSettings>
		<telerik:PickerPopupSelectorSettings AcceptCommand="{Binding Accept}"  
												  CancelCommand="{Binding Cancel}"/>
	</telerik:RadTimePicker.SelectorSettings>
</telerik:RadTimePicker>
 ```

1. Add the namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. Add a sample `ViewModel` class.

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

## See Also

- [Templates]({%slug timepicker-templates%})
- [Selection]({%slug timepicker-selection%})
