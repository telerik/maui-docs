---
title: Commands
page_title: .NET MAUI TimePicker Documentation - Commands
description: Use the exposed commands of the Telerik UI for .NET MAUI TimePicker to programmatically manipulate the display of its popup.
position: 7
previous_url: /controls/timepicker/timepicker-commands
slug: timepicker-commands
---

# .NET MAUI TimePicker Commands

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

## OK and Cancel Buttons

Through the popup or the drop-down, users can pick a time. The time value must be confirmed or rejected with the **OK** or **Cancel** buttons located in the popup or drop-down.

The TimePicker allows you to add a custom logic for the `Accept` and `Cancel` commands which are executed when the **OK** or **Cancel** buttons are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command, which confirms the current selection of the picker and closes the popup or drop-down.
* `CancelCommand`(`ICommand`)&mdash;Defines the command, which rejects the current selection of the picker and closes the popup or drop-down.

You can apply the `Accept` and `Cancel` commands for the popup mode by setting the `PopupSettings` property of the TimePicker. For the drop-down mode, use the `DropDownSettings` property.

The following example shows how to set the `AcceptCommand` and `CancelCommand`.

**1.** Define the TimePicker with `PopupSettings`:

```XAML
<telerik:RadTimePicker x:Name="timePicker">
	<telerik:RadTimePicker.PopupSettings>
		<telerik:PickerPopupSettings AcceptCommand="{Binding Accept}"  
									 CancelCommand="{Binding Cancel}"/>
	</telerik:RadTimePicker.PopupSettings>
</telerik:RadTimePicker>
```

**2.** Add the namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add a sample `ViewModel` class:

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
