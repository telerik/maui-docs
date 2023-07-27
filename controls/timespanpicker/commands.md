---
title: Commands
page_title: .NET MAUI TimeSpanPicker Documentation - Commands
description: Use the exposed commands of the Telerik UI for .NET MAUI TimeSpanPicker to programmatically manipulate the display of its popup.
position: 7
previous_url: /controls/timespanpicker/timespanpicker-commands
slug: timespanpicker-commands
---

# .NET MAUI TimeSpanPicker Commands

The Telerik UI for .NET MAUI TimeSpanPicker exposes a number of commands for programmatic manipulation of its popup rendering.

## TimeSpanPicker Commands

The TimeSpanPicker for .NET MAUI exposes the following commands, which enable you to programmatically manipulate the display of the popup and the clearing of the selected item:

* `ToggleCommand`(`ICommand`)&mdash;Allows you to show and hide the popup. Used for selecting a time interval.
* `ClearCommand`(`ICommand`)&mdash;Allows you to clear the displayed time interval.

The following example shows how to set the `ToggleCommand` and `ClearCommand`.

Define the TimeSpanPicker.

```XAML
<StackLayout>
	<Button Text="Toggle Command" Command="{Binding Source={x:Reference timeSpanPicker}, Path=ToggleCommand}"/>
	<Button Text="Clear Command" Command="{Binding Source={x:Reference timeSpanPicker}, Path=ClearCommand}"/>
	<telerik:RadTimePicker x:Name="timeSpanPicker" />
</StackLayout>
```

Add the namespace.

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```


## PopupSelector Commands

Through the popup, users can pick a time interval. The time interval value has to be confirmed or rejected through the **OK** and **Cancel** buttons that are displayed in the popup.

The TimeSpanPicker allows you to add custom logic for the `Accept` and `Cancel` commands, which are executed when the **OK** and **Cancel** buttons, respectively, are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command which confirms the current selection of the picker and closes the popup.
* `CancelCommand`(`ICommand`)&mdash;Defines the command which rejects the current selection of the picker and closes the popup.

You can apply the `Accept` and `Cancel` commands by using the `SelectorSettings` property of TimeSpanPicker.

The following example shows how to set the `AcceptCommand` and `CancelCommand`.

**1.** Define the TimeSpanPicker.

```XAML
<StackLayout>
    <telerik:RadTimeSpanPicker>
        <telerik:RadTimeSpanPicker.PopupSettings>
            <telerik:PickerPopupSettings AcceptCommand="{Binding Accept}"
                                                      CancelCommand="{Binding Cancel}"/>
        </telerik:RadTimeSpanPicker.PopupSettings>
            <telerik:RadTimeSpanPicker.BindingContext>
                <local:ViewModel/>
            </telerik:RadTimeSpanPicker.BindingContext>
    </telerik:RadTimeSpanPicker>
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

**3**. Add the following namespace.

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```


## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Selection]({%slug timespanpicker-selection%})
