---
title: Styling ItemTemplate and SelectedItemTemplate in ComboBox for UI for .NET MAUI
description: Learn how to style the ItemTemplate and SelectedItemTemplate in ComboBox for UI for .NET MAUI using implicit or explicit styles.
type: how-to
page_title: Style ItemTemplate and SelectedItemTemplate in UI for .NET MAUI ComboBox
meta_title: Style ItemTemplate and SelectedItemTemplate in UI for .NET MAUI ComboBox
slug: style-itemtemplate-selecteditemtemplate-ui-net-maui-combobox
tags: combobox, ui for .net maui, itemtemplate, selecteditemtemplate, styling
res_type: kb
---

## Environment

| Product | Author | 
| --- | ---- | 
| Telerik UI for .NET MAUI ComboBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to style the `Items` and `SelectedItems` in the [ComboBox for UI for .NET MAUI](https://www.telerik.com/maui-ui/documentation/controls/combobox/overview) so I achieve consistency in the appearance across multiple controls without explicitly specifying the styles in each `ItemTemplate` and `SelectedItemTemplate`. I require a solution where implicit or explicit styles define these templates, ensuring a unified look and feel.

This knowledge base article also answers the following questions:
- How to create implicit styles for ComboBox templates in UI for .NET MAUI?
- How to apply consistent styling to `ItemTemplate` and `SelectedItemTemplate` in UI for .NET MAUI ComboBox?
- How to use a single converter for multiple ComboBoxes in UI for .NET MAUI?

## Solution

To achieve consistent styling for multiple ComboBox controls: 
1. Use implicit or explicit styles. 
2. Define the `ItemTemplate` and `SelectedItemTemplate` within the styles. 
3. If the data sources differ across ComboBoxes, apply an `IValueConverter` to format the displayed values.

## Sample Implementation

**1.** Define a resource dictionary containing implicit or explicit styles for the ComboBox, including the `ItemTemplate` and `SelectedItemTemplate`:
    - Use the `DataTemplate` to define the appearance of items and selected items.
    - Apply styles to labels for customization.
    - Use `VisualStateManager` for additional UI states.

```xaml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
			 xmlns:local="clr-namespace:MauiApp14"
             x:Class="MauiApp14.MainPage">
	<ContentPage.Resources>
		<ResourceDictionary>
			<local:ObjectToValueConverter x:Key="ObjectToValueConverter" />

			<Style TargetType="telerik:RadTextInput" x:Key="TextInputStyle">
				<Setter Property="CharacterSpacing" Value="4" />
				<Setter Property="HorizontalTextAlignment" Value="Center" />
			</Style>

			<Style TargetType="telerik:RadTemplatedButton" x:Key="ClearButtonStyle">
				<Setter Property="FontFamily" Value="{x:Static telerik:TelerikFont.Name}" />
				<Setter Property="FontSize" Value="16" />
				<Setter Property="Content" Value="&#xe851;" />
				<Setter Property="TextColor" Value="#A30111"/>
				<Setter Property="VisualStateManager.VisualStateGroups">
					<VisualStateGroupList>
						<VisualStateGroup Name="CommonStates">
							<VisualState Name="Normal" />
							<VisualState Name="PointerOver">
								<VisualState.Setters>
									<Setter Property="telerik:RadTemplatedButton.TextColor" Value="#B53340" />
								</VisualState.Setters>
							</VisualState>
							<VisualState Name="Pressed">
								<VisualState.Setters>
									<Setter Property="telerik:RadTemplatedButton.TextColor" Value="#C76670" />
								</VisualState.Setters>
							</VisualState>
							<VisualState Name="Disabled" />
						</VisualStateGroup>
					</VisualStateGroupList>
				</Setter>
			</Style>
			
			<Style TargetType="telerik:RadTemplatedButton" x:Key="DropDownButtonStyle">
				<Setter Property="BackgroundColor" Value="Transparent" />
				<Setter Property="TextColor" Value="#00897B"/>
			</Style>

			<Style TargetType="Label" x:Key="ComboBoxItemLabelStyle">
				<Setter Property="FontSize" Value="14" />
				<Setter Property="TextColor" Value="Green" />
			</Style>

			<Style TargetType="Label" x:Key="ComboBoxSelectedItemLabelStyle">
				<Setter Property="FontSize" Value="16" />
				<Setter Property="TextColor" Value="DarkGreen" />
			</Style>
			
			<Style TargetType="telerik:RadComboBox">
				<Setter Property="BackgroundColor" Value="LightBlue" />
				<Setter Property="DropDownBackgroundColor" Value="Beige" />
				<Setter Property="HighlightTextColor" Value="Pink" />
				<Setter Property="TextColor" Value="Red" />
				<Setter Property="PlaceholderColor" Value="Blue" />
				<Setter Property="FontSize" Value="Small" />
				<Setter Property="TextInputStyle" Value="{StaticResource TextInputStyle}" />
				<Setter Property="ClearButtonStyle" Value="{StaticResource ClearButtonStyle}" />
				<Setter Property="DropDownButtonStyle" Value="{StaticResource DropDownButtonStyle}" />
				<Setter Property="IsClearButtonVisible" Value="True" />
				<Setter Property="CornerRadius" Value="8" />
				<Setter Property="DropDownCornerRadius" Value="8" />
				<Setter Property="DropDownVerticalOffset" Value="0" />
				<Setter Property="ItemTemplate">
					<Setter.Value>
						<DataTemplate>
							<Label Text="{Binding ., Converter={StaticResource ObjectToValueConverter}}"
                               Style="{StaticResource ComboBoxItemLabelStyle}" />
						</DataTemplate>
					</Setter.Value>
				</Setter>
				<Setter Property="SelectedItemTemplate">
					<Setter.Value>
						<DataTemplate>
							<Label Text="{Binding ., Converter={StaticResource ObjectToValueConverter}}"
                               Style="{StaticResource ComboBoxSelectedItemLabelStyle}" />
						</DataTemplate>
					</Setter.Value>
				</Setter>
			</Style>
		</ResourceDictionary>
	</ContentPage.Resources>
	
	<VerticalStackLayout>
		<telerik:RadComboBox Placeholder="select city" 
							 ItemsSource="{Binding Items}"
							 x:Name="combo"
							 DisplayMemberPath="Name" />
		<telerik:RadComboBox Placeholder="select city" 
							 ItemsSource="{Binding Items2}" 
							 x:Name="combo2"
							 DisplayMemberPath="Name" />
	</VerticalStackLayout>
</ContentPage>
```

**2.** Define `ViewModel` and `DataModel` for the ComboBoxes:

```c#
public class ViewModel
{
    public ViewModel()
    {
        this.Items = new ObservableCollection<City>
        {
            new City { Name = "Tokyo", Population = 13929286 },
            new City { Name = "New York", Population = 8623000 },
            new City { Name = "London", Population = 8908081 },
            new City { Name = "Madrid", Population = 3223334 },
            new City { Name = "Los Angeles", Population = 4000000},
        };

        this.Items2 = new ObservableCollection<Person>
        {
            new Person { Name = "Jake", Country = "USA" },
            new Person { Name = "Mary", Country = "France" },
            new Person { Name = "John", Country = "UK" },
        };
    }
    public ObservableCollection<City> Items { get; set; }
    public ObservableCollection<Person> Items2 { get; set; }
}

public class City
{
    public string Name { get; set; }
    public int Population { get; set; }
}

public class Person
{
    public string Name { get; set; }
    public string Country { get; set; }
}
```


**2.** Use an `IValueConverter` to format the displayed values for different data sources across ComboBoxes.

```C#
public class ObjectToValueConverter : IValueConverter
{
	public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
	{
		// Used for the Person data model for the first ComboBox
		if (value is Person person)
		{
			return person.Name;
		}

		// Used for the City data model for the second ComboBox
		if (value is City city)
		{
			return city.Name;
		}

		// Add IF conditions for all the different ComboBoxes in the application

		return value;
	}

	public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
	{
		throw new NotImplementedException();
	}
}
```

## See Also

- [ComboBox Overview for UI for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/combobox/overview)
- [Style the UI for .NET MAUI ComboBox](https://www.telerik.com/maui-ui/documentation/controls/combobox/styling)
