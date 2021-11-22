---
title: Commands
page_title: .NET MAUI ListPicker Documentation | Commands
description: Check our &quot;Commands&quot; documentation article for Telerik ListPicker for .NET MAUI.
position: 7
slug: listpicker-commands
---

# Commands

## ListPicker Commands

List Picker for .NET MAUI exposes the following commands you can use to programmatically manipulate displaying the popup as well as clearing the selected item:

* `ToggleCommand`(`ICommand`)&mdash;Allows you to show/hide the popup used for selecting an item from a list of items.
* `ClearCommand`(`ICommand`)&mdash;Allows you to clear the displayed item.

## PopupSelector Commands

Through the popup users can pick an item. The date value should be confirmed or rejected through the **OK** and **Cancel** buttons placed on the popup.

The ListPicker allows you to add a custom logic for the `Accept` and `Cancel` commands which are executed when the **OK** and **Cancel** buttons, respectively, are pressed.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command which confirms the current selection of the picker and closes the popup.
* `CancelCommand`(`ICommand`)&mdash;Defines the command which rejects the current selection of the picker and closes the popup.

The `Accept` and `Cancel` commands can be applied using the `SelectorSettings` property of ListPicker.

## Example

The following example demonstrates how to define the ListPicker.

```XAML
<StackLayout>
    <Button Text="Toggle Command" Command="{Binding Source={x:Reference listPicker}, Path=ToggleCommand}"/>
    <Button Text="Clear Command" Command="{Binding Source={x:Reference listPicker}, Path=ClearCommand}"/>
    <telerikInput:RadListPicker Placeholder="Pick a name!"
                                x:Name="listPicker"
                                ItemsSource="{Binding Items}"
                                DisplayMemberPath="FullName">
        <telerikInput:RadListPicker.SelectorSettings>
            <telerikInput:PickerPopupSelectorSettings AcceptCommand="{Binding Accept}"
                                                        CancelCommand="{Binding Cancel}" />
        </telerikInput:RadListPicker.SelectorSettings>
        <telerikInput:RadListPicker.BindingContext>
            <local:ViewModel/>
        </telerikInput:RadListPicker.BindingContext>
    </telerikInput:RadListPicker>
</StackLayout>
```

Set the sample `ViewModel`:

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

Add the Business model:

<snippet id='listpicker-getting-started-business-model' />
```C#
public class Person
{
    public Person(string name, string lastName)
    {
        this.Name = name;
        this.LastName = lastName;
    }

    public string Name { get; set; }

    public string LastName { get; set; }

    public string FullName
    {
        get
        {
            return $"{this.Name} {this.LastName}";
        }
    }
}
```

Add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Selection]({%slug listpicker-selection%})
- [Templates]({%slug listpicker-templates%})
