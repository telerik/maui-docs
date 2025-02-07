---
title: Grouping CollectionView by One Property and Displaying Another in .NET MAUI
description: Learn how to group items in a CollectionView by one property and display a different property in the group header in .NET MAUI.
type: how-to
page_title: How to Group CollectionView by One Property and Display Another in .NET MAUI
slug: group-collectionview-display-another-property-net-maui
tags: collectionview, grouping, .net maui, displaymemberpath, groupheader, converter
res_type: kb
---

## Environment

| Versions | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In a .NET MAUI application, I need to group items in a CollectionView based on one property but display another property in the group header. How can I achieve this customization?

This knowledge base article also answers the following questions:
- How to use a converter in a CollectionView group header template in .NET MAUI?
- How to customize the display of grouped items in CollectionView?
- How to bind to a different property in the CollectionView group header?

## Solution

To group items in a CollectionView by one property and display a different property in the group header, follow these steps:

1. Define a converter that will map the property used for grouping to the property you wish to display. This converter will be used in the group header template.

2. Apply the converter to the binding in the group header template to display the desired property.

### Define the Converter

Create a converter that maps the grouping property to the desired display property. Here's an example of a `CountryNameToFlagConverter` that maps country names to their corresponding flag images.

```csharp
public class CountryNameToFlagConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var countriesAndFlags = new Dictionary<string, string>();
        for (int i = 1; i <= 5; i++)
        {
            countriesAndFlags.Add($"Country {i}", $"flag_{i}.png");
        }

        if (value == null || !countriesAndFlags.ContainsKey((string)value))
        {
            return countriesAndFlags.First().Value;
        }

        var countryName = (string)value;
        return countriesAndFlags[countryName];
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
```

### Customize the Group Header Template

Use the converter within the `GroupHeaderTemplate` of the CollectionView to display the desired property instead of the default grouping property.

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <local:CountryNameToFlagConverter x:Key="CountryNameToFlagConverter" />
    </ResourceDictionary>
</ContentPage.Resources>
<telerik:RadCollectionView ItemsSource="{Binding Items}" x:Name="grid">
    <telerik:RadCollectionView.GroupDescriptors>
        <telerik:PropertyGroupDescriptor PropertyName="Country"/>
    </telerik:RadCollectionView.GroupDescriptors>
    <telerik:RadCollectionView.GroupHeaderTemplate>
        <DataTemplate>
            <HorizontalStackLayout BackgroundColor="LightBlue" Spacing="20">
                <Label Text="{Binding Key}" />
                <Image Source="{Binding Key, Converter={StaticResource CountryNameToFlagConverter}}" />
            </HorizontalStackLayout>
        </DataTemplate>
    </telerik:RadCollectionView.GroupHeaderTemplate>
</telerik:RadCollectionView>
```

### Add Sample Data to the CollectionView

Finally, populate the CollectionView with sample data that includes the properties you are grouping by and the properties you wish to display.

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();

        var items = new ObservableCollection<City>();

        for (int group = 1; group <= 5; group++)
        {
            for (int index = 1; index <= 5; index++)
            {
                var city = new City($"Country {group}", $"City {index}", $"Data {index}");
                items.Add(city);
            }
        }

        this.grid.ItemsSource = items;
    }
}

public class City
{
    public City(string country, string name, string data)
    {
        Country = country;
        Name = name;
        Data = data;
    }

    public string Country { get; }
    public string Name { get; }
    public string Data { get; }
}
```

By following these steps, you can group items in a CollectionView by one property and display a different property in the group header.

## See Also

- [Grouping in CollectionView](https://docs.telerik.com/devtools/maui/controls/collectionview/grouping/header)
- [Data Binding in .NET MAUI](https://docs.microsoft.com/en-us/dotnet/maui/fundamentals/data-binding/)
- [IValueConverter Interface](https://docs.microsoft.com/en-us/dotnet/api/system.windows.data.ivalueconverter)
