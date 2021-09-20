---
title: Delegate Group Descriptor
page_title: .NET MAUI ListView Documentation | Grouping
description: Check our &quot;Delegate Group Descriptor&quot; documentation article for Telerik ListView for .NET MAUI.
position: 2
slug: listview-delegate-group-descriptor
description: Describing RadListView grouping feature
tags: group, radlistview, groupdescriptor
---

# Grouping

**RadListView** provides you with the functionality to programmatically group its data at runtime. This can be achieved through adding groupdescriptors to the **RadListView.GroupDescriptors** collection.

* **PropertyGroupDescriptor**
* **DelegateGroupDescriptor**

## DelegateGroupDescriptor 

This descriptor enables you to group by a custom key (e.g. some complex expression combining two or more properties) instead of being limited by the value of a single property. This descriptor exposes the following properties:

- **KeyExtractor**: Defines the `(Func<object, object)` delegate which returns the property to retrieve the group key for each data item.
- **SortOrder**:  Defines the sort order in each group to Ascending or Descending.

Let's use the same example from the previous section, just add DelegateGroupDescriptor through code instead. 

**1** RadListView definition:

```XAML
 <telerikDataControls:RadListView x:Name="listView" 
                                             ItemsSource="{Binding Cities}"
                                             ItemTemplate="{StaticResource ListViewItemTemplate}"
                                             GroupHeaderTemplate="{StaticResource ListViewGroupHeaderTemplate}"
                                             GroupHeaderStyle="{StaticResource ListViewGroupHeaderStyle}">
    <telerikDataControls:RadListView.BindingContext>
        <local:GroupingViewModel/>
    </telerikDataControls:RadListView.BindingContext>
</telerikDataControls:RadListView>
```

**2** Add the namespaces:

```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
```

**3** Create and apply a delegate for grouping the items (for example by their first letter) as following:

```C#
var delegateDescriptor = new DelegateGroupDescriptor
{
    KeyExtractor = FirstLetterKeyExtractor
};

listView.GroupDescriptors.Add(delegateDescriptor);



private object FirstLetterKeyExtractor(object arg)
{
    var item = arg as City;
    return item?.Name.Substring(0, 1);
}
```

**4** Add a business model:

```C#
public class City
{
    public string Continent { get; set; }
    public string Name { get; set; }
    public string Country { get; set; }
}
```

**5** Add a ViewModel with a collection of Cities:

```C#
public class GroupingViewModel : NotifyPropertyChangedBase
{
    public ObservableCollection<City> Cities { get; set; }

    public GroupingViewModel()
    {
        this.Cities = new ObservableCollection<City>()
        {
            new City() { Name = "Barcelona", Country = "Spain", Continent = "Europe"},
            new City() { Name = "Madrid", Country = "Spain", Continent = "Europe" },
            new City() { Name = "Rome", Country = "Italy", Continent = "Europe" },
            new City() { Name = "Florence", Country = "Italy", Continent = "Europe" },
            new City() { Name = "London", Country = "England", Continent = "Europe" },
            new City() { Name = "Manchester", Country = "England", Continent = "Europe"},
            new City() { Name = "New York", Country = "USA", Continent = "North America" },
            new City() { Name = "Boston", Country = "USA",  Continent = "North America" }
         };
    }
}
```

#### Figure 1: ListView grouped through DelegateGroupDescriptor
![ListView Grouping](../images/listview_grouping_delegatedescriptor.png)

>important You can find a working demo labeled **Delegate Group Descriptors** in the ListView/Bindable Collections folder of the [SDKBrowser MAUI application]({%slug developer-focused-examples%}). 

## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
