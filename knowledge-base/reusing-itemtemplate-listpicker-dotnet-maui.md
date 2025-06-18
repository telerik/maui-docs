---
title: Reusing ItemTemplate with ListPicker in .NET MAUI
description: Learn how to reuse a single ItemTemplate across multiple ListPickers in .NET MAUI using a value converter for dynamic data binding.
type: how-to
page_title: Reusing ItemTemplate Across ListPickers in .NET MAUI
meta_title: Reusing ItemTemplate Across ListPickers in .NET MAUI
slug: reusing-itemtemplate-listpicker-dotnet-maui
tags: listpicker, .net maui, itemtemplate, displaymemberpath, converter
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI ListPicker | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to reuse a single ItemTemplate across multiple instances of the [ListPicker]({%slug listpicker-overview%}) in my .NET MAUI application. Each ListPicker uses the `DisplayMemberPath` property but displays different types of data. I want to avoid manually overriding the `ItemTemplate` for each `RadListPicker` and instead define an implicit `ItemTemplate` that uses a value converter to display the correct data based on the ListPicker's data source.

This knowledge base article also answers the following questions:
- How to use a common `ItemTemplate` for multiple `RadListPickers`?
- How to dynamically bind the displayed text using `DisplayMemberPath`?
- How to define an implicit `ItemTemplate` in `RadListPicker`?

## Solution

To achieve this, use a value converter to dynamically bind the displayed text based on the type of data in the `RadListPicker`. Follow these steps:


**1.** Define the `RadListPickers` and set their `ItemTemplate` property to a static resource.

```xaml
<VerticalStackLayout>
    <telerik:RadListPicker x:Name="picker"
                           DisplayMemberPath="Country"
                           Placeholder="Picker 1"
                           ItemTemplate="{StaticResource commontemplate}" />
    <telerik:RadListPicker x:Name="picker2"
                           Placeholder="Picker 2"
                           DisplayMemberPath="Name"
                           ItemTemplate="{StaticResource commontemplate}" />
</VerticalStackLayout>
```

**2.** Create classes for the data types used by the `RadListPickers`.

```csharp
class Person2
{
    public string Name { get; set; }
    public string Country { get; set; }
}

class Country2
{
    public string Name { get; set; }
}
```

**3.** Populate the ListPickers with data in the page's constructor.

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();

        var people = new List<Person2>
        {
            new Person2 { Name = "John", Country = "USA" },
            new Person2 { Name = "Mary", Country = "UK" },
            new Person2 { Name = "Jake", Country = "Australia" }
        };
        picker.ItemsSource = people;

        var countries = new List<Country2>
        {
            new Country2 { Name = "Great Britain" },
            new Country2 { Name = "UK" },
            new Country2 { Name = "Spain" }
        };
        picker2.ItemsSource = countries;
    }
}
```

**4.** Create a value converter to dynamically bind the displayed text.

```csharp
public class ObjectToValueConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        if (value is Person2 person)
        {
            return person.Country;
        }

        if (value is Country2 country)
        {
            return country.Name;
        }

        return value;
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
```

**5.** Define a single `DataTemplate` in XAML that uses the value converter.

```xaml
<ContentPage.Resources>
    <ResourceDictionary>
        <local:ObjectToValueConverter x:Key="ObjectToValueConverter" />
        <DataTemplate x:Key="commontemplate">
            <Grid RowDefinitions="*"
                  ColumnDefinitions="*"
                  HorizontalOptions="Fill">
                <Label Text="{Binding ., Converter={StaticResource ObjectToValueConverter}}" />
            </Grid>
        </DataTemplate>
    </ResourceDictionary>
</ContentPage.Resources>
```

This approach allows you to reuse the same `ItemTemplate` across multiple ListPickers by dynamically binding the displayed text based on the data source.

## See Also

- [ListPicker Overview]({%slug listpicker-overview%})
- [Data Binding in .NET MAUI](https://docs.microsoft.com/en-us/dotnet/maui/fundamentals/data-binding/)
- [Using Value Converters in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/data-binding/converters)
