---
title: ItemStyle Selector
page_title: .NET MAUI ListView Documentation | ItemStyle Selector
description: Check our &quot;ItemStyle Selector&quot; documentation article for Telerik ListView for .NET MAUI.
position: 1
previous_url: /controls/listview/styling/listview-features-style-selector
slug: listview-features-style-selector
---

# ItemStyle Selector

The ListView component exposes conditional styling feature. It allows users to apply a different `Style` to each item depending on a specific condition.

## Example

The following example will demonstrate how to apply the `Conditional Styling` in the ListView control. Let's add the RadlistView component and create a simple data.

1. Set up the ListView control:

 ```XAML
 <telerikDataControls:RadListView x:Name="listView"
                                  ItemsSource="{Binding Source}">
    <telerikDataControls:RadListView.BindingContext>
        <local:ViewModel />
    </telerikDataControls:RadListView.BindingContext>
    <telerikDataControls:RadListView.ItemTemplate>
        <DataTemplate>
            <telerikListView:ListViewTemplateCell>
                <telerikListView:ListViewTemplateCell.View>
                    <StackLayout>
                        <Label Margin="10" Text="{Binding Name}" />
                        <Label Margin="10"
                               FontSize="10"
                               Text="{Binding Age}" />
                    </StackLayout>
                </telerikListView:ListViewTemplateCell.View>
            </telerikListView:ListViewTemplateCell>
        </DataTemplate>
    </telerikDataControls:RadListView.ItemTemplate>

    <telerikDataControls:RadListView.ItemStyleSelector>
        <local:ExampleListViewStyleSelector />
    </telerikDataControls:RadListView.ItemStyleSelector>
</telerikDataControls:RadListView>
 ```

1. Create a simple data for the ListView component:

 ```C#
 public class Person
 {
	public Person(string name, int age)
	{
		this.Name = name;
		this.Age = age;
	}

	public string Name { get; set; }

	public int Age { get; set; }
 }

 public class ViewModel
 {
	public ViewModel()
	{
		this.Source = new List<Person> {
			new Person("Tom", 25),
			new Person("Anna",18),
			new Person("Peter",43),
			new Person("Teodor",29),
			new Person("Lorenzo",65),
			new Person("Andrea",79),
			new Person("Martin",5) };
	}

	public List<Person> Source { get; set; }
 }
 ```

1. You can set a different style for a specific item by using the `ListViewStyleSelector` class. We can use the `OnSelectStyle` method to change the styles of the items in the ListView control. A sample implementation of a custom class that derives from `ListViewStyleSelector` and overrides its `OnSelectStyle` method is shown below:

 ```C#
 public class ExampleListViewStyleSelector : ListViewStyleSelector
 {
    protected override void OnSelectStyle(object item, ListViewStyleContext styleContext)
    {
        var style = new ListViewItemStyle
        {
            BackgroundColor = Colors.Transparent
        };

        styleContext.ItemStyle = style;
        styleContext.SelectedItemStyle = new ListViewItemStyle
        {
            BackgroundColor = Colors.Gray,
            BorderColor = Colors.Red,
            BorderWidth = 2
        };

        var sourceItem = item as Person;
        if (sourceItem.Age < 18)
        {
            styleContext.ItemStyle.BackgroundColor = Colors.Blue;
        }
        else if (sourceItem.Age < 65)
        {
            styleContext.ItemStyle.BackgroundColor = Colors.Green;
        }
    }
 }
 ```

The following image shows how the ListView control will look like when conditional styling is used.

![StyleSelector](../images/listview-features-style-selector.png "Style Selector")

>important The **SDK Browser** application contains an example that shows the `StyleSelector` feature in the ListView control.

## See Also

- [Selection]({%slug listview-features-selection%})
- [Styling]({%slug listview-features-styling%})
- [Reordering]({%slug listview-features-reorder-items%})
