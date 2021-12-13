---
title: Selection
page_title: .NET MAUI ListPicker Documentation | Selection
description: Check our &quot;Selection&quot; documentation article for Telerik ListPicker for .NET MAUI.
position: 5
slug: listpicker-selection
---

# Selection

The ListPicker for .NET MAUI enables the application users to quickly and easily select an item from a list of items. This topic will go through the provided by the ListPicker API related to item selection.

## Important Properties

The `SelectedItem`(`object`) property specifies the selected item of the ListPicker.

## Methods

The ListPicker for .NET MAUI allows you to clear the selected date/time through its `ClearSelection` method.

The following example demonstrates how to use the `ClearSelection` method of the ListPicker.

1. Define the ListPicker:

 ```XAML
<StackLayout>
    <Button Text="Clear Selection" Clicked="OnClearSelectionClicked"/>
    <telerikInput:RadListPicker x:Name="listPicker"
                                Placeholder="Pick a name!"
                                ItemsSource="{Binding Items}"
                                DisplayMemberPath="FullName">
        <telerikInput:RadListPicker.BindingContext>
            <local:ViewModel/>
        </telerikInput:RadListPicker.BindingContext>
        <telerikInput:RadListPicker.ItemTemplate>
            <DataTemplate>
                <Label Text="{Binding Name}"
                       HorizontalTextAlignment="Center"
                       VerticalTextAlignment="Center"/>
            </DataTemplate>
        </telerikInput:RadListPicker.ItemTemplate>
    </telerikInput:RadListPicker>
</StackLayout>
 ```

1. Clear the selection inside the button `click` event:

 ```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.listPicker.ClearSelection();
}
 ```

1. Set a sample `ViewModel`:

 <snippet id='listpicker-getting-started-viewmodel' />

1. Define the Business model:

 <snippet id='listpicker-getting-started-business-model' />

1. Add the following namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input"
 ```

## Events

The ListPicker for .NET MAUI exposes a `SelectionChanged` event which is raised when the user confirms the selected item.

The following example demonstrates how to use the `SelectionChanged` event of the ListPicker.


1. Define the ListPicker:

 ```XAML
<telerikInput:RadListPicker Placeholder="Pick a name!"
	                        ItemsSource="{Binding Items}"
	                        SelectionChanged="RadListPicker_SelectionChanged"
	                        DisplayMemberPath="FullName">
    <telerikInput:RadListPicker.BindingContext>
        <local:ViewModel/>
    </telerikInput:RadListPicker.BindingContext>
    <telerikInput:RadListPicker.ItemTemplate>
        <DataTemplate>
            <Label Text="{Binding Name}"
				   HorizontalTextAlignment="Center"
				   VerticalTextAlignment="Center"/>
        </DataTemplate>
    </telerikInput:RadListPicker.ItemTemplate>
</telerikInput:RadListPicker>
 ```

1. Set the `SelectionChanged` event, where `sender` corresponds to the ListPicker control:

 ```C#
private void RadListPicker_SelectionChanged(object sender, System.EventArgs e)
{
	// implement your logic here
}
 ```

1. Define a sample `ViewModel`:

 <snippet id='listpicker-getting-started-viewmodel' />
 ```C#
public class CitiesViewModel
{
    public CitiesViewModel()
    {
        this.Items = new ObservableCollection<City>
        {
            new City { Name = "Tokyo", Population = 13929286 },
            new City { Name = "New York", Population = 8623000 },
            new City { Name = "London", Population = 8908081 },
            new City { Name = "Madrid", Population = 3223334 },
            new City { Name = "Los Angeles", Population = 4000000},
            new City { Name = "Paris", Population = 2141000 },
            new City { Name = "Beijing", Population = 21540000 },
            new City { Name = "Singapore", Population = 5612000 },
            new City { Name = "New Delhi", Population = 18980000 },
            new City { Name = "Bangkok", Population = 8305218 },
            new City { Name = "Berlin", Population = 3748000 },
        };
    }

    public ObservableCollection<City> Items { get; set; }
}
 ```

1. Set the Business model. In the example, the `sender` is the ListPicker control.

 <snippet id='listpicker-getting-started-business-model' />
 ```C#
public class City
{
    public string Name { get; set; }
    public int Population { get; set; }
}
 ```

1. Add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility""
```

## See Also

- [Commands]({%slug listpicker-commands%})
