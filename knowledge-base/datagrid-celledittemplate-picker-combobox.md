---
title: Pickers and ComboBoxes in DataGrid CellEditTemplate
description: how to use pickers and comboboxes in celledit template
type: how-to
page_title: How to define pickers and comboboxes in datagrid cell edit template
slug: datagrid-celledittemplate-picker-combobox
position: 
tags: maui, datagrid, celledit template, combobox, picker
ticketid: 1605456
res_type: kb
---

## Environment
| Version | Product | Author | 
| --- | --- | ---- | 
| 5.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

The purpose of this how-to article is to show how to define pickers and comboboxes in DataGrid CellEdit Template. For this purpose we will need a helper class with attached property. This class will handle when the binding of the source and selected items to be removed and set. 

## Solution

XAML definition of the RadDataGrid:

```XAML
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             xmlns:local="clr-namespace:MauiApp28"
             x:Class="MauiApp28.MainPage">

    <ContentPage.Resources>
        <DataTemplate x:Key="ComboTemplate">
            <telerik:RadComboBox local:DataGridUtils.EditorBindingItem="{Binding Item}" />
        </DataTemplate>
    </ContentPage.Resources>

    <Grid>
        <telerik:RadDataGrid x:Name="dataGrid"
                             ItemsSource="{Binding Clubs}"
                             AutoGenerateColumns="False">
            <telerik:RadDataGrid.Columns>
                <telerik:DataGridTextColumn PropertyName="Name" />
                <telerik:DataGridTextColumn PropertyName="NumRegs" CellEditTemplate="{StaticResource ComboTemplate}" />
                <telerik:DataGridTimeColumn PropertyName="Time" />
            </telerik:RadDataGrid.Columns>
        </telerik:RadDataGrid>
    </Grid>
    
</ContentPage>
```

The ViewModel used: 

```C#
public class ViewModel
{
    private ObservableCollection<Club> clubs;
    public ObservableCollection<Club> Clubs => clubs ?? (clubs = CreateClubs());
    private ObservableCollection<Club> CreateClubs()
    {
        return new ObservableCollection<Club>
        {
            new Club("Text 1", new TimeSpan(3, 28, 33)),
            new Club("Text 2", new TimeSpan(2, 56, 44)),
        };
    }
}
```
The DataModel used:

```C#
public class Club : NotifyPropertyChangedBase
{
    private string name;
    private TimeSpan time;
    private string numregs;
    private List<string> comboList;

    public Club(string name, TimeSpan time)
    {
        Name = name;
        Time = time;
        comboList = new List<string>() { "One", "Two" };
        numregs = "One";
    }
    public string Name
    {
        get { return this.name; }
        set { this.UpdateValue(ref this.name, value); }
    }

    public TimeSpan Time
    {
        get { return this.time; }
        set { this.UpdateValue(ref this.time, value); }
    }
    public List<string> ComboList
    {
        get { return this.comboList; }
        set { this.UpdateValue(ref this.comboList, value); }
    }
    public string NumRegs
    {
        get { return this.numregs; }
        set { this.UpdateValue(ref this.numregs, value); }
    }
}
```
And the helper class called DataGridUtils:

```C#
public static class DataGridUtils
{
    public static readonly BindableProperty EditorBindingItemProperty = BindableProperty.CreateAttached(
        "EditorBindingItem", typeof(object), typeof(DataGridUtils), null, propertyChanged: OnEditorBindingItemChanged);

    public static object GetEditorBindingItem(BindableObject bindable)
    {
        return bindable.GetValue(EditorBindingItemProperty);
    }

    public static void SetEditorBindingItem(BindableObject bindable, object value)
    {
        bindable.SetValue(EditorBindingItemProperty, value);
    }

    private static void OnEditorBindingItemChanged(BindableObject bindable, object oldValue, object newValue)
    {
        if (bindable is RadComboBox radComboBox)
        {
            HandleRadComboBox(radComboBox, newValue);
        }
        else if (bindable is Picker picker)
        {
            HandlePicker(picker, newValue);
        }
    }

    private static void HandleRadComboBox(RadComboBox combo, object newValue)
    {
        //// Clear the SelectedItem binding first, so that it does not become null when we clear the ItemsSource.
        combo.RemoveBinding(RadComboBox.SelectedItemProperty);
        combo.RemoveBinding(RadComboBox.ItemsSourceProperty);

        if (newValue is Club club)
        {
            //// Set the ItemsSource binding first, so that when the SelectedItem binding kicks in, there is a valid ItemsSource.
            combo.SetBinding(RadComboBox.ItemsSourceProperty, new Binding { Path = nameof(Club.ComboList), Source = club });
            combo.SetBinding(RadComboBox.SelectedItemProperty, new Binding { Path = nameof(Club.NumRegs), Source = club });
        }
    }

    private static void HandlePicker(Picker picker, object newValue)
    {
        //// Clear the SelectedItem binding first, so that it does not become null when we clear the ItemsSource.
        picker.RemoveBinding(Picker.SelectedItemProperty);
        picker.RemoveBinding(Picker.ItemsSourceProperty);

        if (newValue is Club club)
        {
            //// Set the ItemsSource binding first, so that when the SelectedItem binding kicks in, there is a valid ItemsSource.
            picker.SetBinding(Picker.ItemsSourceProperty, new Binding { Path = nameof(Club.ComboList), Source = club });
            picker.SetBinding(Picker.SelectedItemProperty, new Binding { Path = nameof(Club.NumRegs), Source = club });
        }
    }
}
```

