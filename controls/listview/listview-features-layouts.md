---
title: Layouts
page_title: .NET MAUI ListView Documentation | Layouts
description: Check our &quot;Layouts&quot; documentation article for Telerik ListView for .NET MAUI control.
position: 10
slug: listview-features-layouts
---

# Layouts

RadListView control supports two layouts: linear and grid through the `LayoutDefinition` property. It accepts values of type ListViewLayoutBase which is a base class for all list view layouts. 

Here are the properties exposed by the ListViewLayoutBase class: 

- **VerticalItemSpacing** (double): Gets or sets the vertical space between two items.
- **HorizontalItemSpacing** (double): Gets or sets the horizontal space between two items.
- **ItemLength** (double): Gets or sets the width or height (depending on the layout orientation) of the items. The default value is -1 which means that the items will be sized according to the targeted platform default behavior.
- **GroupHeaderLength** (double): Gets or sets the width or height (depending on the layout orientation) of the group headers. The default value is -1 which means that the items will be sized according to the targeted platform default behavior.
- **Orientation** (Orientation): Gets or sets the orientation (scroll direction) of the layout.

## Linear Layout

Linear layout is the default layout of the control. It can be explicitly set by creating an instance of the **ListViewLinearLayout** class and assigning it to the **RadListView.LayoutDefinition** property.

### Example

This example will demonstrate how to use the **RadListViewLinearLayout**.

Here is the list view definition in XAML:

<snippet id='listview-layouts-linearlayout-listview'/>
```XAML
<telerikDataControls:RadListView x:Name="listView" 
								 ItemsSource="{Binding Items}">
	<telerikDataControls:RadListView.BindingContext>
		<local:ViewModel/>
	</telerikDataControls:RadListView.BindingContext>
	<telerikDataControls:RadListView.ItemTemplate>
		<DataTemplate>
			<telerikListView:ListViewTemplateCell>
				<telerikListView:ListViewTemplateCell.View>
					<telerik:RadBorder BorderColor="LightBlue" BorderThickness="2">
						<Label Text="{Binding Name}"/>
					</telerik:RadBorder>
				</telerikListView:ListViewTemplateCell.View>
			</telerikListView:ListViewTemplateCell>
		</DataTemplate>
	</telerikDataControls:RadListView.ItemTemplate>
	<telerikDataControls:RadListView.LayoutDefinition>
		<telerikListView:ListViewLinearLayout ItemLength="40" VerticalItemSpacing="2" />
	</telerikDataControls:RadListView.LayoutDefinition>
</telerikDataControls:RadListView>
```

Where:

<snippet id='xmlns-teleriklistview'/>
```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
```

Add the ViewModel class with the ItemsSource collection:

<snippet id='listview-layouts-linearlayout-source'/>
```C#
public class Item
{
	public string Name { get; set; }
	public Color Color { get; set; }
}
	
public class ViewModel
{
	public ViewModel()
	{
		this.Items = new ObservableCollection<Item>();
		for (int i = 0; i < 14; i++)
		{
			var c = 200 - 10 * i;
			this.Items.Add(new Item() { Name = "Item " + i, });
		}
	}
	public ObservableCollection<Item> Items { get; set; }
}
```

This is the result:

![Linear Vertical](images/listview-layouts-linear.png)

## Grid Layout

The Grid Layout allows distributing cells in a fixed number of columns/rows. It exposes the following properties in addition to the basic layout properties:

- **SpanCount** (int): Gets or sets the count of the columns / rows (depending on the orientation) of the list. 

The grid layout can be utilized by setting the **RadListView.LayoutDefinition** property to a new instance of the **ListViewGridLayout** class.

### Example

This example will demonstrate how to use the **RadListViewGridLayout**.

Here is the list view definition in XAML:

<snippet id='listview-layouts-gridlayout-listview'/>
```XAML
<telerikDataControls:RadListView x:Name="listView" ItemsSource="{Binding Items}">
	<telerikDataControls:RadListView.BindingContext>
		<local:ViewModel/>
	</telerikDataControls:RadListView.BindingContext>
	<telerikDataControls:RadListView.ItemTemplate>
		<DataTemplate>
			<telerikListView:ListViewTemplateCell>
				<telerikListView:ListViewTemplateCell.View>
					<telerik:RadBorder BorderColor="LightBlue" BorderThickness="2">
						<Label Text="{Binding Name}"/>
					</telerik:RadBorder>
				</telerikListView:ListViewTemplateCell.View>
			</telerikListView:ListViewTemplateCell>
		</DataTemplate>
	</telerikDataControls:RadListView.ItemTemplate>
	<telerikDataControls:RadListView.LayoutDefinition>
		<telerikListView:ListViewGridLayout ItemLength="40" 
											HorizontalItemSpacing="2" 
											VerticalItemSpacing="2" />
	</telerikDataControls:RadListView.LayoutDefinition>
</telerikDataControls:RadListView>
```

Where:

<snippet id='xmlns-teleriklistview'/>
```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
```

Add the ViewModel class with the ItemsSource collection:

<snippet id='listview-layouts-gridlayout-source'/>
```C#
public class Item
{
	public string Name { get; set; }
	public Color Color { get; set; }
}
	
public class ViewModel
{
	public ViewModel()
	{
		this.Items = new ObservableCollection<Item>();
		for (int i = 0; i < 14; i++)
		{
			var c = 200 - 10 * i;
			this.Items.Add(new Item() { Name = "Item " + i, });
		}
	}
	public ObservableCollection<Item> Items { get; set; }
}
```

This is the result:

![Linear Vertical](images/listview-layouts-grid.png)

## See Also

- [ListView TextCell]({% slug listview-textcell %})
- [ListView TemplateCell]({% slug listview-templatecell %})
- [Cell Swipe]({% slug listview-features-cell-swipe %})
- [Pull to Refresh]({% slug listview-features-pull-to-refresh %})
- [Reorder Items]({% slug listview-features-reorder-items %})