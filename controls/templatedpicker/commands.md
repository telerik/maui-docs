---
title: Commands
page_title: .NET MAUI TemplatedPicker Documentation - Commands
description:  Use the exposed commands of the Telerik UI for .NET MAUI TemplatedPicker to programmatically manipulate the display of its popup and clear selected dates or handle date selection acceptance or cancellation.
position: 7
previous_url: /controls/templatedpicker/templatedpicker-commands
slug: templatedpicker-commands
---

# .NET MAUI TemplatedPicker Commands

Telerik UI for .NET MAUI TemplatedPicker exposes a number of commands for programmatic manipulation of its popup rendering.

## TemplatedPicker Commands

The TemplatedPicker for .NET MAUI exposes the following commands, which enable you to programmatically manipulate the display of the popup and the clearing of the selected item:

* `ToggleCommand`&mdash;Allows you to show/hide the popup. Used for selecting an item from the custom picker.
* `ClearCommand`&mdash;Allows you to clear the displayed item.

## OK and Cancel Buttons

Through the popup or the drop-down, users can pick an item. This must be confirmed or rejected with the **OK** or **Cancel** buttons located in the popup or drop-down.

The TemplatedPicker allows you to add a custom logic for the `Accept` and `Cancel` commands which are executed when the **OK** or **Cancel** buttons are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command, which confirms the current selection of the picker and closes the popup or drop-down. Use `AcceptCommandParameter` to pass a parameter to the command execute method. 
* `CancelCommand`(`ICommand`)&mdash;Defines the command, which rejects the current selection of the picker and closes the popup or drop-down. Use `CancelCommandParameter` to pass a parameter to the command execute method.

You can apply the `Accept` and `Cancel` commands for the popup mode by setting the `PopupSettings` property of the TemplatedPicker. For the drop-down mode, use the `DropDownSettings` property.

## Example

The example shows how to define the commands in the `PopupSettings`. The same is valid for the `DropDownSettings`.

**1.** Define the TemplatedPicker:

```XAML
<VerticalStackLayout>
    <Button Text="Toggle Command" Command="{Binding Source={x:Reference picker}, Path=ToggleCommand}"/>
    <Button Text="Clear Command" Command="{Binding Source={x:Reference picker}, Path=ClearCommand}"/>
    <telerik:RadTemplatedPicker x:Name="picker" PickerMode="Popup">
        <telerik:RadTemplatedPicker.SelectorTemplate>
            <ControlTemplate>
                <telerik:RadCalendar SelectedDate="{TemplateBinding SelectedValue, Mode=TwoWay}"/>
            </ControlTemplate>
        </telerik:RadTemplatedPicker.SelectorTemplate>
		<telerik:RadTemplatedPicker.PopupSettings>
                <telerik:PickerPopupSettings AcceptCommand="{Binding Accept}"
                                             CancelCommand="{Binding Cancel}"/>
            </telerik:RadTemplatedPicker.PopupSettings>
            <telerik:RadTemplatedPicker.BindingContext>
                <local:ViewModel/>
            </telerik:RadTemplatedPicker.BindingContext>
    </telerik:RadTemplatedPicker>
</VerticalStackLayout>
```

**2.** Set a sample `ViewModel`:

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

**3.** Set the defined `ViewModel` as a `BindingContext` of the page:

```C#
this.BindingContext = new ViewModel();
```

**4.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```


## See Also

- [Events]({%slug templatedpicker-events%})
- [Templates]({%slug templatedpicker-templates%})
