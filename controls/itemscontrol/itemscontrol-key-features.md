---
title: Key Features
page_title: .NET MAUI ItemsControl Documentation | Key Features for .NET MAUI Button
description: Check our &quot;Key Features&quot; documentation article for Telerik ItemsControl for .NET MAUI.
position: 2
tags: .net maui, telerik .net maui, ui for .net maui, button, microsoft .net maui
slug: itemscontrol-key-features
---

# Key Features

The purpose of this help article is to show you the key features of the **RadItemsControl** control. 

## Define RadItemsControl

Add RadButton definition in XAML:

```XAML
<telerikMauiControls:RadItemsControl/>
```

Add the following namespace:

```XAML
xmlns:telerikMauiControls="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

## Set ItemsSource

**ItemsSource** property defines the collection of the items that will populate the ItemsControl. 

Let's for example use the following data item:

```C#
public class Experience
{
	public string Title { get; set; }
	public string Company { get; set; }
}
```

Create a ViewModel class and define a collection of `Experience` objects:

```C#
public class ViewModel
{
    public ViewModel()
    {
        this.Experiences = new ObservableCollection<Experience>()
        {
            new Experience() { Title = "JS Developer", Company = "@ Progress Software" },
            new Experience() { Title = "Technical Support Engineer", Company = "@ Progress Software" },
            new Experience() { Title = "Junior Technical Support Engineer", Company = "@ Progress Software" },
        };
    }

    public ObservableCollection<Experience> Experiences { get; set; }
}
```

Add the RadItemsControl definition with ItemsSource and sample ItemTemplate applied:

```XAML
<telerikMauiControls:RadItemsControl x:Name="itemsControl"
							      ItemsSource="{Binding Experiences, Mode=TwoWay}">
	<telerikMauiControls:RadItemsControl.BindingContext>
		<local:ViewModel />
	</telerikMauiControls:RadItemsControl.BindingContext>
	<telerikMauiControls:RadItemsControl.ItemTemplate>	
		<DataTemplate>	
			<StackLayout Margin="10"
						 Spacing="5"
						 Orientation="Horizontal">
				<Label Text="{Binding Title}" 
							   FontSize="14"/>
				<Label Text="{Binding Company}"
							   TextColor="#99000000" 
							   FontSize="12"/>
			</StackLayout>
		</DataTemplate>
	</telerikMauiControls:RadItemsControl.ItemTemplate>
</telerikMauiControls:RadItemsControl>
```

Check the result below:

![](images/itemscontrol-itemssource.png)

## Apply ItemTemplate

Through the **ItemTemplate** property you can fully customize the way your data is visualized - you can place various controls inside in order to achieve more appealing designs.

The example below shows the same scenario with the `Experience` objects from [Set ItemsSource](#set-itemssource) section with slightly modified ItemTemplate with [RadBorder control]({%slug button-overview%}):

```XAML
<telerikMauiControls:RadItemsControl x:Name="itemsControl"
                                ItemsSource="{Binding Experiences, Mode=TwoWay}">
    <telerikMauiControls:RadItemsControl.BindingContext>
        <local:ViewModel />
    </telerikMauiControls:RadItemsControl.BindingContext>
    <telerikMauiControls:RadItemsControl.ItemTemplate>
        <DataTemplate>
            <telerikMauiControls:RadBorder BorderColor="#DFDFDF"
                                           BorderThickness="0, 0, 0, 1">
                <StackLayout Margin="10"
                        Spacing="5">
                    <Label Text="{Binding Title}" 
                            FontSize="14"/>
                    <Label Text="{Binding Company}"
                            TextColor="#99000000" 
                            FontSize="12"/>
                </StackLayout>
            </telerikPrimitives:RadBorder>
        </DataTemplate>
    </telerikMauiControls:RadItemsControl.ItemTemplate>
</telerikMauiControls:RadItemsControl>
```

#### Telerik Button for .NET MAUI

![](images/itemscontrol-itemtemplate.png)

## See Also

- [Getting Started]({% slug maui-getting-started%})
