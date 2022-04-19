---
title: TemplateCell
page_title: .NET MAUI ListView Documentation | Cell Types
description: Check our &quot;Cell Types&quot; documentation article for Telerik ListView for .NET MAUI control.
position: 2
previous_url: /controls/listview/cells/listview-templatecell
slug: listview-templatecell
---

# TemplateCell

Cells in the ListView are the presentation of each data item from the control's `ItemsSource`. You can choose between the `ListViewTextCell` and `ListViewTemplateCell` cell types.

The `ListViewTemplateCell` derives from `Xamarin.Forms.ViewCell` and used to present complex data sets as `RadListView.ItemTemplate`.

The example below demonstrates how to create a ListView with templated cells, like this:

![](../images/listview-celltypes-templatecell.png)

1. Create a view model that will be the source of the ListView:

 ```C#
public class Book
{
	public string Title { get; set; }
	public string Author { get; set; }
	public bool IsFavourite { get; set; }
}
public class ViewModel
{
	public ViewModel()
	{
		this.Source = new List<Book>{
			new Book{ Title = "The Fault in Our Stars ",  Author = "John Green"},
			new Book{ Title = "Divergent",  Author = "Veronica Roth"},
			new Book{ Title = "Gone Girl",  Author = "Gillian Flynn", IsFavourite = true},
			new Book{ Title = "Clockwork Angel",  Author = "Cassandra Clare"},
			new Book{ Title = "The Martian",  Author = "Andy Weir"},
			new Book{ Title = "Ready Player One",  Author = "Ernest Cline"},
			new Book{ Title = "The Lost Hero",  Author = "Rick Riordan", IsFavourite = true},
			new Book{ Title = "All the Light We Cannot See",  Author = "Anthony Doerr"},
			new Book{ Title = "Cinder",  Author = "Marissa Meyer"},
			new Book{ Title = "Me Before You",  Author = "Jojo Moyes"},
			new Book{ Title = "The Night Circus",  Author = "Erin Morgenstern"},
		};
	}

	public List<Book> Source { get; set; }
}
 ```

1. Define the ListView control either in XAML or in code behind.

**Define the ListVew in XAML**

```XAML
<telerikDataControls:RadListView ItemsSource="{Binding Source}" x:Name="listView">
	<telerikDataControls:RadListView.BindingContext>
		<local:ViewModel />
	</telerikDataControls:RadListView.BindingContext>
	<telerikDataControls:RadListView.ItemTemplate>
		<DataTemplate>
			<telerikListView:ListViewTemplateCell>
				<telerikListView:ListViewTemplateCell.View>
					<Grid>
						<HorizontalStackLayout Margin="10, 10, 10, 0">
							<Image IsVisible="{Binding IsFavourite}" Source="favourite.png" HeightRequest="16" VerticalOptions="Center" />
							<Label Text="{Binding Title}" FontSize="16" FontAttributes="Bold" TextColor="Black" VerticalOptions="Center" />
						</HorizontalStackLayout>
						<HorizontalStackLayout Grid.Row="1" Margin="10, 0, 10, 10">
							<Label Text="by" FontSize="13" FontAttributes="Italic" TextColor="Gray" />
							<Label Text="{Binding Author}" FontSize="13" FontAttributes="Italic" TextColor="Gray" />
						</HorizontalStackLayout>
					</Grid>
				</telerikListView:ListViewTemplateCell.View>
			</telerikListView:ListViewTemplateCell>
		</DataTemplate>
	</telerikDataControls:RadListView.ItemTemplate>
	<telerikDataControls:RadListView.LayoutDefinition>
		<telerikListView:ListViewLinearLayout ItemLength="60" />
	</telerikDataControls:RadListView.LayoutDefinition>
</telerikDataControls:RadListView>
```

1. Add the needed namespaces:

 ```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
 ```						

**Define the ListView in code-behind**

For clarity, let's build the template of the list view cell in a separate method:

```C#
public View GetCellContent()
{
    var content = new Grid();

    var book = new Label
    {
        FontAttributes = FontAttributes.Bold,
        TextColor = Color.Black,
        FontSize = 16,
        VerticalOptions = LayoutOptions.Center
    };

    book.SetBinding(Label.TextProperty, new Binding(nameof(Book.Title)));

    var fav = new Image
    {
        Source = ImageSource.FromFile("favourite.png"),
        HeightRequest = 16,
        VerticalOptions = LayoutOptions.Center
    };

    fav.SetBinding(Image.IsVisibleProperty, new Binding(nameof(Book.IsFavourite)));

    var author = new Label
    {
        TextColor = Color.Gray,
        FontAttributes = FontAttributes.Italic,
        FontSize = 13
    };

    author.SetBinding(Label.TextProperty, new Binding(nameof(Book.Author)));

    var by = new Label
    {
        Text = "by",
        TextColor = Color.Gray,
        FontAttributes = FontAttributes.Italic,
        FontSize = 13
    };

    var main = new StackLayout { Orientation = StackOrientation.Horizontal, Margin = new Thickness(10, 10, 10, 0) };
    main.Children.Add(fav);
    main.Children.Add(book);

    var detail = new StackLayout { Orientation = StackOrientation.Horizontal, Margin = new Thickness(10, 0, 10, 10) };
    detail.Children.Add(by);
    detail.Children.Add(author);

    content.Children.Add(main, 0, 0);
    content.Children.Add(detail, 0, 1);

    return content;
}
```

Define the ListVew:

```C#
var listView = new RadListView
{
    ItemsSource = new ViewModel().Source,
    ItemTemplate = new DataTemplate(() =>
    {
        return new ListViewTemplateCell
        {
            View = GetCellContent()
        };
    }),
};
```


## See Also

- [ListView Item TemplateSelector]({%slug listview-item-template-selector%})
- [ListView Layouts]({% slug listview-features-layouts %})
- [Items Styling]({% slug listview-features-styling %})
