---
title: Header and Footer
page_title: .NET MAUI ListView Documentation | Header and Footer
description: Check our &quot;Header and Footer&quot; documentation article for Telerik ListView for .NET MAUI
position: 7
slug: listview-features-header-footer
---

# Header and Footer

RadListView provides the option to add - **Header** and **Footer**, which will allow you to position content of your choice above and below the list with the items. Both header and footer templates are scrolled along with the ListView items. 

* **HeaderTemplate**(DataTemplate): Defines the Header of the ListView before all items.
* **FooterTemplate**(DataTemplate): Defines the Footer of the ListView after all items.

## Example

Here is an example how to add Header and Footer to the RadListView control.

**1** Create a ViewModel:

```C#
public class HeaderAndFooterViewModel
{
    public HeaderAndFooterViewModel()
    {
        this.Items = GetItems(20);
    }

    public ObservableCollection<string> Items { get; set; }

    private static ObservableCollection<string> GetItems(int count)
    {
        var items = new ObservableCollection<string>();
        for (int i = 0; i < count; i++)
        {
            items.Add(string.Format("item {0}", i));
        }

        return items;
    }
}
```

**2** Add the following sample DataTemplates to the resources of the page that will be used as:

**HeaderTemplate**:

```XAML
<DataTemplate x:Key="HeaderTemplate">
    <Label Text="The Available Items are: " 
           TextColor="Black" 
           FontAttributes="Bold" 
           FontSize="25"/>
</DataTemplate>
```

**FooterTemplate**:

```XAML
 <DataTemplate x:Key="FooterTemplate">
    <Label Text="All Items!" 
           TextColor="Black" 
           FontAttributes="Bold" 
           FontSize="25"/>
</DataTemplate>
```

**3** Use the following snippet to declare the RadListView in XAML:

```XAML
<telerikDataControls:RadListView x:Name="listView" 
                                     ItemsSource="{Binding Items}"
                                     HeaderTemplate="{StaticResource HeaderTemplate}" 
                                     FooterTemplate="{StaticResource FooterTemplate}"/>
```

Here is how the ListView Header looks:

![RadListView Footer Template](images/listview-features-header-template.png "[RadListView Footer Template")

and the ListView Footer:

![RadListView Footer Template](images/listview-features-footer-template.png "[RadListView Footer Template")

>important A sample Header and Footer example can be found in the **SDKBrowser MAUI application**.

## See Also

- [Events]({%slug listview-features-events%})
- [Selection]({%slug listview-features-selection%})
- [Reordering]({%slug listview-features-reorder-items%})
