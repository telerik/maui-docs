---
title: Change ListView GridLayout SpanCount
description: 
type: how-to
page_title: Binding in the ListView GridLayour SpanCount
slug: listview-gridlayout-spancount-binding
position: 
tags: 
ticketid: 1606449
res_type: kb
---

## Environment

| Product | Author | 
| --- | ---- | 
| Telerik UI for .NET MAUI ListView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 


## Description

This article explains how to use the `SpanCount` property of the RadListView GridLayoutDefinition with Binding.

## Solution

`SpanCount` is a bindable property, just the ListViewGridLayout does not receive the binding context of the ListView directly. You can explicitly set it like this:

```XAML
<telerik:RadListView.LayoutDefinition>
    <telerik:ListViewGridLayout Orientation="Horizontal"
                            SpanCount="{Binding BindingContext.SpanCountValue, Source={x:Reference listView}}"
                            HorizontalItemSpacing="15"
                            ItemLength="120"/>
</telerik:RadListView.LayoutDefinition>
```

## Example

The example below shows how the `SpanCount` can be updated according to another value changed from a NumericInput control.

**1.** Here is the deifnition of the controls in XAML:

```XAML
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="60" />
        <RowDefinition Height="*" />
    </Grid.RowDefinitions>
    <telerik:RadNumericInput Minimum="1" 
                                    Maximum="6" 
                                    Value="{Binding SpanCountValue, Mode=TwoWay}"
                                    Step="1"/>
    <telerik:RadListView x:Name="listView"
                                    ItemsSource="{Binding Items}"
                                    Grid.Row="1">
        <telerik:RadListView.ItemTemplate>
            <DataTemplate>
                <telerik:ListViewTextCell Text="{Binding Name}"
                                                TextColor="Black" DetailColor="Gray" />
            </DataTemplate>
        </telerik:RadListView.ItemTemplate>
        <telerik:RadListView.LayoutDefinition>
            <telerik:ListViewGridLayout Orientation="Horizontal"
                                        SpanCount="{Binding BindingContext.SpanCountValue, Source={x:Reference listView}}"
                                        HorizontalItemSpacing="15"
                                        ItemLength="120"/>
        </telerik:RadListView.LayoutDefinition>
    </telerik:RadListView>
</Grid>
```

**2.** The ViewModel - implements property changed and the DataModel used:

```C#
public class ViewModel : NotifyPropertyChangedBase
{
    private int span = 3;
    public ViewModel()
    {
        this.Items = new ObservableCollection<Item>();
        for (int i = 0; i < 40; i++)
        {
            var c = 200 - 10 * i;
            this.Items.Add(new Item() { Name = "Item " + i, });
        }
    }
    public int SpanCountValue
    {
        get => this.span;
        set
        {
            if(this.span != value)
            {
                this.span = value;
                OnPropertyChanged();
            }  
        }
    }
    public ObservableCollection<Item> Items { get; set; }
}
public class Item
{
    public string Name { get; set; }
}
```

**3.** Set the Bindingcontext

```C#
public partial class MainPage : ContentPage
{
    ViewModel vm;
	public MainPage()
	{
		InitializeComponent();
        this.vm = new ViewModel();
        this.BindingContext = vm;
	}
}
```

## See Also

-[ListView Layouts]({%slug listview-features-layouts%}})
