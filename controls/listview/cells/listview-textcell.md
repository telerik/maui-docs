---
title: ListView TextCell
page_title: .NET MAUI ListView Documentation | Cell Types
description: Check our &quot;Cell Types&quot; documentation article for Telerik ListView for .NET MAUI control.
position: 1
slug: listview-textcell
---

# ListView TextCell

Cells in RadListView are the presentation of each data item from the control's ItemsSource. You can choose between two types of cells - ListViewTextCell and ListViewTemplateCell.

**ListViewTextCell** derives from Xamarin.Forms.**TextCell** and displays text. It can optionally render detail text as a second row within a list view item. This is the default cell of the RadListView.

The example below demonstrates how to create a list view with text cells, like this:

![](../images/listview-celltypes-textcell.png)

**1.** Create a view model that will be the source of the list view:

<snippet id='listview-celltypes-textcell-viewmodel'/>
```C#
public class Book
{
	string Title { get; set; }
	string Author { get; set; }
}

public class ViewModel
{
	public ViewModel()
	{
		this.Source = new List<Book>{
		new Book{ Title = "The Fault in Our Stars ",  Author = "John Green"},
		new Book{ Title = "Divergent",  Author = "Veronica Roth"},
		new Book{ Title = "Gone Girl",  Author = "Gillian Flynn"},
		new Book{ Title = "Clockwork Angel",  Author = "Cassandra Clare"},
		new Book{ Title = "The Martian",  Author = "Andy Weir"},
		new Book{ Title = "Ready Player One",  Author = "Ernest Cline"},
		new Book{ Title = "The Lost Hero",  Author = "Rick Riordan"},
		new Book{ Title = "All the Light We Cannot See",  Author = "Anthony Doerr"},
		new Book{ Title = "Cinder",  Author = "Marissa Meyer"},
		new Book{ Title = "Me Before You",  Author = "Jojo Moyes"},
		new Book{ Title = "The Night Circus",  Author = "Erin Morgenstern"},
		};
	}

	public List<Book> Source { get; set; }
}
```

**2.** Add the definition of the ListView control:
	
<snippet id='listview-celltypes-textcell-listview-xaml'/>
<snippet id='listview-celltypes-textcell-listview-csharp'/>
```XAML
<telerikDataControls:RadListView ItemsSource="{Binding Source}" x:Name="listView">
	<telerikDataControls:RadListView.BindingContext>
		<local:ViewModel />
	</telerikDataControls:RadListView.BindingContext>
	<telerikDataControls:RadListView.ItemTemplate>
		<DataTemplate>
			<telerikListView:ListViewTextCell Text="{Binding Title}" 
											  Detail="{Binding Author}" 
											  TextColor="Black" 
											  DetailColor="Gray" />
		</DataTemplate>
	</telerikDataControls:RadListView.ItemTemplate>
	<telerikDataControls:RadListView.LayoutDefinition>
		<telerikListView:ListViewLinearLayout ItemLength="60" />
	</telerikDataControls:RadListView.LayoutDefinition>
</telerikDataControls:RadListView>
```
	
**3.** Add the following namespaces:
	
```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also
- [TemplateCell]({%slug listview-textcell%})
- [ItemTemplate Selector]({%slug listview-item-template-selector%})
- [Layouts]({% slug listview-features-layouts %})
- [Items Styling]({% slug listview-features-styling %})
