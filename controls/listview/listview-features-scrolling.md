---
title: Scrolling
page_title: .NET MAUI ListView Documentation | Scrolling
description: Check our &quot;Scrolling&quot; documentation article for Telerik ListView for .NET MAUI control.
position: 9
slug: listview-features-scrolling
description: Describing how to scroll RadListView to a certain item
tags: programmatic, scrolling
---

# Scrolling

## Vertical ScrollBar

You can set the visibility of ListView vertical scrollbar according to your preferences with the `VerticalScrollBarVisibility` property.

* **VerticalScrollBarVisibility**(*Xamarin.Forms.ScrollBarVisibility*): Specifies whether the vertical scrollbar will be visualized. By default it is set to ScrollBarVisibility.Default which means the scrollbar behavior depends on the target platform.

Here is a quick snippet on how you can set it to ScrollBarVisibility.Always:

```XAML
<telerikDataControls:RadListView x:Name="listView" 
                                 VerticalScrollBarVisibility="Always" />
```
```C#
var listView = new RadListView();
listView.VerticalScrollBarVisibility = ScrollBarVisibility.Always;
```

## Programmatic Scrolling

RadListView exposes the following method for programmatic scrolling to a specific data item: 

* **ScrollItemIntoView(object item)**: Attempts to bring the specified data item into the view.

## Example

Check below a simple example of `ScrollItemIntoView` usage inside a button click event handler.

Here is a sample view with a ListView control and a button:

<snippet id='listview-features-programmatic-scrolling-xaml'/>
```XAML
<Grid Margin="10">
	<Grid.RowDefinitions>
		<RowDefinition Height="Auto"/>
		<RowDefinition/>
	</Grid.RowDefinitions>
	<StackLayout>
		<Button Clicked="ScrollItemIntoViewClicked" 
				Text="ScrollItemIntoView"/>
		<Label x:Name="label"/>
	</StackLayout>
	<telerikDataControls:RadListView x:Name="listView" 
									 Grid.Row="1" 
									 ItemsSource="{Binding Items}">
		<telerikDataControls:RadListView.BindingContext>
			<local:ViewModel />
		</telerikDataControls:RadListView.BindingContext>
	</telerikDataControls:RadListView>
</Grid>
```

Use the following ViewModel to create a simple data for the ListView component:

<snippet id='listview-features-programmatic-scrolling'/>
```C#
public class ViewModel
{
	public ViewModel()
	{
		this.Items = new ObservableCollection<string>();

		for (int i = 0; i < 100; i++)
		{
			this.Items.Add("Item " + i);
		}
	}
	public ObservableCollection<string> Items { get; set; }
}
```

Create the button click event handler and inside this method use `ScrollItemIntoView` to navigate to a concrete item:

<snippet id='listview-features-programmatic-scrolling-scroll-to-item-method'/>
```C#
private void ScrollItemIntoViewClicked(object sender, EventArgs e)
{
	var rnd = new Random();
	var items = this.listView.ItemsSource as ObservableCollection<string>;
	var item = items[rnd.Next(items.Count - 1)];
	this.label.Text = "Scrolled to: " + item;
	this.listView.ScrollItemIntoView(item);
}
```
	
And the end result:

![](images/listview-features-scrolling.png)
	
## See Also

- [Selection]({%slug listview-features-selection%})
- [Grouping]({%slug listview-features-grouping%})
- [Reordering]({%slug listview-features-reorder-items%})