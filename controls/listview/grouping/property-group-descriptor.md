---
title: Property Group Descriptor
page_title: .NET MAUI ListView Documentation | Grouping
description: Check our &quot;Property Group Descriptor&quot; documentation article for Telerik ListView for .NET MAUI.
position: 1
slug: listview-property-group-descriptor
previous_url: /controls/listview/grouping/listview-property-group-descriptor
description: Describing RadListView grouping feature
tags: group, radlistview, groupdescriptor
---

# Grouping

The ListView provides the functionality to programmatically group its data at runtime. This can be achieved through adding `GroupDescriptors` to the `RadListView.GroupDescriptors` collection.

There are two types of grouping, using:

* `PropertyGroupDescriptor`
* `DelegateGroupDescriptor`

## PropertyGroupDescriptor

You can group the data by a property value from the class that defines your items. This descriptor exposes the following properties:

- `PropertyName`&mdash;Defines the string name of the property you want to group by.
- `SortOrder`&mdash;Defines the sort order in each group to Ascending or Descending.

1. Add the following business object:

 ``` C#
public class City
{
    public string Continent { get; set; }
    public string Name { get; set; }
    public string Country { get; set; }
}
 ```

1. Add a `ViewModel` with a collection of Cities:

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

1. Group the Cities by the `Country` property through the `PropertyGroupDescriptor`:

 ```XAML
<telerikDataControls:RadListView x:Name="listView" ItemsSource="{Binding Cities}"
                                     ItemTemplate="{StaticResource ListViewItemTemplate}"
                                     GroupHeaderTemplate="{StaticResource ListViewGroupHeaderTemplate}"
                                     GroupHeaderStyle="{StaticResource ListViewGroupHeaderStyle}">
    <telerikDataControls:RadListView.BindingContext>
        <local:GroupingViewModel/>
    </telerikDataControls:RadListView.BindingContext>
    <telerikDataControls:RadListView.GroupDescriptors>
        <telerikListView:PropertyGroupDescriptor PropertyName="Country"/>
    </telerikDataControls:RadListView.GroupDescriptors>
</telerikDataControls:RadListView>
 ```

1. Add the `Templates` definition in the page resources:

 ```XAML
<ResourceDictionary>
    <DataTemplate x:Key="ListViewItemTemplate">
        <telerikListView:ListViewTemplateCell>
            <telerikListView:ListViewTemplateCell.View>
                <Grid Padding="16, 0, 0, 0" BackgroundColor="#F1F2F5">
                    <Label Text="{Binding Name}" TextColor="#6F6F70" FontSize="Small" />
                </Grid>
            </telerikListView:ListViewTemplateCell.View>
        </telerikListView:ListViewTemplateCell>
    </DataTemplate>
    <DataTemplate x:Key="ListViewGroupHeaderTemplate">
        <Grid>
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="Auto" />
                <ColumnDefinition />
            </Grid.ColumnDefinitions>
            <Label Text="&#x25B8;" Margin="8, 12, 0, 6" TextColor="DarkGray" FontSize="Medium">
                <Label.Triggers>
                    <DataTrigger TargetType="Label" Binding="{Binding IsExpanded}" Value="True">
                        <Setter Property="Text" Value="&#x25BE;" />
                    </DataTrigger>
                </Label.Triggers>
            </Label>
            <Label Margin="0, 12, 0, 6" Text="{Binding }" Grid.Column="1" TextColor="DarkGray" FontSize="Medium" HorizontalOptions="Start" />
        </Grid>
    </DataTemplate>
    <telerikListView:ListViewGroupStyle x:Key="ListViewGroupHeaderStyle" BackgroundColor="Transparent" />
</ResourceDictionary>
 ```

1. The namespaces used:

 ```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
 ```


>important For a **Property Group Descriptor** demo, refer to the **ListView/Grouping** folder of the [SDKBrowser .NET MAUI application]({%slug maui-demo-app%}).

## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
