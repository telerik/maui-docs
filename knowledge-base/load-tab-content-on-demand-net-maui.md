---
title: Loading Tab Content on Demand in .NET MAUI TabView
description: Learn how to load the content of TabView items on demand as the user selects tabs, improving performance for UI-heavy content in .NET MAUI applications.
type: how-to
page_title: Implementing On-Demand Content Loading in .NET MAUI TabView
slug: load-tab-content-on-demand-net-maui
tags: tabview, .net maui, on-demand loading, itemtemplate, contenttemplate
res_type: kb
ticketid: 1668168
---

## Environment

<table>
<tbody>
<tr>
<td>Product</td>
<td>TabView for .NET MAUI, <br />Version 7.0.0</td>
</tr>
</tbody>
</table>

## Description

When using a [TabView](https://docs.telerik.com/devtools/maui/controls/tabview/overview) bound to an `ItemSource` with an `ItemTemplate`, loading UI-heavy content for each tab during page load can negatively impact performance. To enhance application responsiveness, it's beneficial to load the content of each tab item on demand, only when the user selects it.

This KB article also answers the following questions:
- How to improve performance by loading tab content on demand in .NET MAUI TabView?
- How to delay the loading of UI-heavy content in TabView tabs until selection?
- How to use attached properties for on-demand content loading in TabView?

## Solution

To load tab item content on demand, create a `TabViewUtils` class with two attached properties: `LoadOnDemand` and `LoadOnDemandTemplate`. 

### Implementing the Attached Properties

First, implement the `TabViewUtils` class with the necessary attached properties:

```C#
public static class TabViewUtils
{
    public static readonly BindableProperty LoadOnDemandProperty = BindableProperty.CreateAttached(
        "LoadOnDemand", typeof(bool), typeof(TabViewUtils), false, propertyChanged: LoadOnDemandChanged);
        
    public static readonly BindableProperty LoadOnDemandTemplateProperty = BindableProperty.CreateAttached(
        "LoadOnDemandTemplate", typeof(DataTemplate), typeof(TabViewUtils), null);

    public static bool GetLoadOnDemand(BindableObject bindable) => (bool)bindable.GetValue(LoadOnDemandProperty);
    public static void SetLoadOnDemand(BindableObject bindable, bool value) => bindable.SetValue(LoadOnDemandProperty, value);

    public static DataTemplate GetLoadOnDemandTemplate(BindableObject bindable) => (DataTemplate)bindable.GetValue(LoadOnDemandTemplateProperty);
    public static void SetLoadOnDemandTemplate(BindableObject bindable, DataTemplate value) => bindable.SetValue(LoadOnDemandTemplateProperty, value);

    private static void LoadOnDemandChanged(BindableObject bindable, object oldValue, object newValue)
    {
        var tv = (RadTabView)bindable;
        tv.PropertyChanged -= RadTabView_PropertyChanged;

        if ((bool)newValue)
        {
            tv.PropertyChanged += RadTabView_PropertyChanged;
            UpdateSelectedItemContentTemplate(tv);
        }
    }

    private static void RadTabView_PropertyChanged(object sender, PropertyChangedEventArgs args)
    {
        if (args.PropertyName == nameof(RadTabView.SelectedItem))
        {
            UpdateSelectedItemContentTemplate((RadTabView)sender);
        }
    }

    private static void UpdateSelectedItemContentTemplate(RadTabView tv)
    {
        if (tv.SelectedItem != null && tv.SelectedItem.ContentTemplate == null)
        {
            tv.SelectedItem.ContentTemplate = GetLoadOnDemandTemplate(tv.SelectedItem);
        }
    }
}
```

### Setting the TabItems DataTemplate

Add the following DataTemplate to the page's resources:

```XAML
<DataTemplate x:Key="TabViewItemContentTemplate">
    <telerik:RadItemsControl ItemsSource="{Binding Customers}">
        <telerik:RadItemsControl.ItemTemplate>
            <DataTemplate>
                <Grid>
                    <telerik:RadBorder BorderColor="LightGray"
                                    Padding="10"
                                    Margin="10,5"
                                    BorderThickness="1" 
                                    CornerRadius="5">
                        <Grid RowDefinitions="Auto, Auto" 
                            RowSpacing="5">
                            <HorizontalStackLayout Spacing="10">
                                <Label Text="&#xe836;"
                                    FontFamily="TelerikFontExamples" />
                                <Label Text="{Binding Name}" />
                            </HorizontalStackLayout>
                            <HorizontalStackLayout Spacing="10"
                                                Grid.Row="1">
                                <Label Text="&#xe85d;"
                                    FontFamily="TelerikFontExamples" />
                                <Label Text="{Binding Number}" />
                            </HorizontalStackLayout>
                        </Grid>
                    </telerik:RadBorder>
                </Grid>
            </DataTemplate>
        </telerik:RadItemsControl.ItemTemplate>
    </telerik:RadItemsControl>
</DataTemplate>
```

### Setting Up the TabView in XAML

Define your `TabView` in XAML and apply the attached properties to enable on-demand content loading:

```XAML
<telerik:RadTabView x:Name="tabView"
                ItemsSource="{Binding Data}"
                local:TabViewUtils.LoadOnDemand="True">
    <telerik:RadTabView.ItemTemplate>
        <DataTemplate>
            <telerik:TabViewItem HeaderText="{Binding Name}"
                                local:TabViewUtils.LoadOnDemandTemplate="{StaticResource TabViewItemContentTemplate}" />
        </DataTemplate>
    </telerik:RadTabView.ItemTemplate>
</telerik:RadTabView>
```

### Sample ViewModel and Data Model

Ensure your ViewModel and data model are set up to provide data to the `TabView`. Here's an example:

```C#
public class ViewModel
{
    public ViewModel()
    {
        Data = new ObservableCollection<Location>
        {
            // Sample data

        };
    }
    public ObservableCollection<Location> Data { get; set; }
}

public class Location
{
    public string Name { get; set; }
    public ObservableCollection<Customer> Customers { get; set; }
}

public class Customer
{
    public string Name { get; set; }
    public int Number { get; set; }
}
```

Using the `LoadOnDemand` and `LoadOnDemandTemplate` attached properties, you can efficiently manage the loading of tab content, significantly improving the performance and responsiveness of applications with UI-heavy tab content.

## See Also

- [TabView Overview](https://docs.telerik.com/devtools/maui/controls/tabview/overview)
- [TabView Data Binding Example](https://docs.telerik.com/devtools/maui/controls/tabview/datatabinding)
