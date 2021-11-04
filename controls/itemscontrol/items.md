---
title: Items
page_title: .NET MAUI ItemsControl Documentation | Items for .NET MAUI ItemsControl
description: "Set the items of the Telerik UI for .NET MAUI ItemsControl and populate them with data."
position: 2
tags: .net maui, telerik .net maui, ui for .net maui, microsoft .net maui
slug: itemssource_itemscontrol
---

# Items

The ItemsControl enables you to define the collection of the items that will be rendered.

To set the items of the ItemsControl and populate them with data, use its **ItemsSource** property:

1. Use the following data item:

 ```C#
public class Experience
{
	public string Title { get; set; }
	public string Company { get; set; }
}
 ```

1. Create a `ViewModel` class and define a collection of `Experience` objects:

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

1. Add the ItemsControl definition with the `ItemsSource` and a sample `ItemTemplate` applied:

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

The following image shows the end result.

![](images/itemscontrol-itemssource.png)

## See Also

- [Getting Started with Telerik UI for .NET MAUI ItemsControl]({% slug get_started_itemscontrol %})
- [Setting the Items Template of the ItemsControl]({% slug templates_itemscontrol %})
