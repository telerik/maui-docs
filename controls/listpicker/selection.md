---
title: Selection
page_title: .NET MAUI ListPicker Documentation - Selection
description: Learn more about the selection functionality that the Telerik UI for .NET MAUI ListPicker control provides.

position: 5
slug: listpicker-selection
previous_url: /controls/listpicker/listpicker-selection
---

# .NET MAUI ListPicker Selection

The ListPicker for .NET MAUI enables the application users to select an item from a list of items. This topic will go through the provided by the ListPicker API related to item selection.

## Selected Item Properties

The `SelectedItem`(`object`) property specifies the selected item of the ListPicker.

## Clear Button

You can enable a Clear button which can be used to quickly remove the selected value. To enable the button, set `IsClearButtonVisible` property of the DateTimePicker:

```XAML
<telerik:RadListPicker IsClearButtonVisible="True" />
```

## Methods

The ListPicker for .NET MAUI allows you to clear the selected date/time through its `ClearSelection` method.

The following example demonstrates how to use the `ClearSelection` method of the ListPicker.

**1.** Define the ListPicker:

```XAML
<VerticalStackLayout>
    <Button Text="Clear Selection" Clicked="OnClearSelectionClicked"/>
    <telerik:RadListPicker x:Name="listPicker"
                                Placeholder="Pick a name!"
                                ItemsSource="{Binding Items}"
                                DisplayMemberPath="FullName">
        <telerik:RadListPicker.BindingContext>
            <local:ViewModel/>
        </telerik:RadListPicker.BindingContext>
        <telerik:RadListPicker.ItemTemplate>
            <DataTemplate>
                <Label Text="{Binding Name}"
                       HorizontalTextAlignment="Center"
                       VerticalTextAlignment="Center"/>
            </DataTemplate>
        </telerik:RadListPicker.ItemTemplate>
    </telerik:RadListPicker>
</VerticalStackLayout>
```

**2.** Clear the selection inside the button `click` event:

```C#
private void OnClearSelectionClicked(object sender, EventArgs e)
{
    this.listPicker.ClearSelection();
}
```

**3.** Set a sample `ViewModel`:

<snippet id='listpicker-getting-started-viewmodel' />

**4.** Define the Business model:

<snippet id='listpicker-getting-started-business-model' />

**5.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Events

The ListPicker for .NET MAUI exposes a `SelectionChanged` event which is raised when the user confirms the selected item.

The following example demonstrates how to use the `SelectionChanged` event of the ListPicker.


**1.** Define the ListPicker:

```XAML
<telerik:RadListPicker Placeholder="Pick a name!"
	                        ItemsSource="{Binding Items}"
	                        SelectionChanged="RadListPicker_SelectionChanged"
	                        DisplayMemberPath="FullName">
    <telerik:RadListPicker.BindingContext>
        <local:ViewModel/>
    </telerik:RadListPicker.BindingContext>
    <telerik:RadListPicker.ItemTemplate>
        <DataTemplate>
            <Label Text="{Binding Name}"
				   HorizontalTextAlignment="Center"
				   VerticalTextAlignment="Center"/>
        </DataTemplate>
    </telerik:RadListPicker.ItemTemplate>
</telerik:RadListPicker>
```

**2.** Set the `SelectionChanged` event, where `sender` corresponds to the ListPicker control:

```C#
private void RadListPicker_SelectionChanged(object sender, System.EventArgs e)
{
	// implement your logic here
}
```

**3.** Define a sample `ViewModel`:

<snippet id='listpicker-getting-started-viewmodel' />

**4.** Set the Business model. In the example, the `sender` is the ListPicker control.

<snippet id='listpicker-getting-started-business-model' />

**5.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [Commands]({%slug listpicker-commands%})
