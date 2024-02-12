---
title: Commands
page_title: .NET MAUI ListPicker Documentation - Commands
description: Use the exposed commands of the Telerik UI for .NET MAUI ListPicker to programmatically manipulate the display of its popup and clear selected dates or accept or cancel the date selection.
position: 7
previous_url: /controls/listpicker/listpicker-commands
slug: listpicker-commands
---

# .NET MAUI ListPicker Commands

This article describes the commands available in the Telerik UI for .NET MAUI ListPicker control. 

## ListPicker Commands

List Picker for .NET MAUI exposes the following commands you can use to programmatically manipulate displaying the popup as well as clearing the selected item:

* `ToggleCommand`(`ICommand`)&mdash;Allows you to show/hide the popup used for selecting an item from a list of items.
* `ClearCommand`(`ICommand`)&mdash;Allows you to clear the displayed item.

## OK and Cancel Buttons

Through the popup or the drop-down, users can pick an item. This must be confirmed or rejected with the **OK** or **Cancel** buttons located in the popup or drop-down.

The ListPicker allows you to add a custom logic for the `Accept` and `Cancel` commands which are executed when the **OK** or **Cancel** buttons are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command, which confirms the current selection of the picker and closes the popup or drop-down. Use the `AcceptCommandParameter` to pass a parameter to the command execute method. 
* `CancelCommand`(`ICommand`)&mdash;Defines the command, which rejects the current selection of the picker and closes the popup or drop-down. Use the `CancelCommandParameter` to pass a parameter to the command execute method.

You can apply the `Accept` and `Cancel` commands for the popup mode by setting the `PopupSettings` property of the ListPicker. For the drop-down mode, use the `DropDownSettings` property.

## Example

**1.** Define the ListPicker.

```XAML
<StackLayout>
    <Button Text="Toggle Command" Command="{Binding Source={x:Reference listPicker}, Path=ToggleCommand}"/>
    <Button Text="Clear Command" Command="{Binding Source={x:Reference listPicker}, Path=ClearCommand}"/>
    <telerik:RadListPicker Placeholder="Pick a name!"
                                x:Name="listPicker"
                                ItemsSource="{Binding Items}"
                                DisplayMemberPath="FullName">
        <telerik:RadListPicker.PopupSettings>
            <telerik:PickerPopupSettings AcceptCommand="{Binding Accept}"
                                         CancelCommand="{Binding Cancel}" />
        </telerik:RadListPicker.PopupSettings>
        <telerik:RadListPicker.BindingContext>
            <local:ViewModel/>
        </telerik:RadListPicker.BindingContext>
    </telerik:RadListPicker>
</StackLayout>
```

**2.** Set the sample `ViewModel`:

```C#
public class ViewModel
{
    public ViewModel()
    {
        this.Items = new ObservableCollection<Person>()
        {
            new Person("Freda","Curtis"),
            new Person("Jeffery","Francis"),
            new Person("Ema","Lawson"),
            new Person("Niki","Samaniego"),
            new Person("Jenny","Santos"),
            new Person("Eric","Wheeler"),
            new Person("Emmett","Fuller"),
            new Person("Brian","Johnas"),
        };

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

    public ObservableCollection<Person> Items { get; set; }
    public ICommand Accept { get; set; }
    public ICommand Cancel { get; set; }
}
```

**3.** Add the Business model:

<snippet id='listpicker-getting-started-business-model' />

**4.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [Selection]({%slug listpicker-selection%})
- [Templates]({%slug listpicker-templates%})
