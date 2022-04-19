---
title: Multi-Level Grouping
page_title: .NET MAUI ListView Documentation | Grouping
description: Check our &quot;Multi-Level Grouping&quot; documentation article for Telerik ListView for .NET MAUI
position: 5
slug: listview-grouping-multilevel
previous_url: /controls/listview/grouping/listview-grouping-multilevel
description: Describing RadListView grouping feature
tags: group, radlistview, groupdescriptor, multilevel
---

# Multi-Level Grouping

This article provides an overview on how you could enable multi-level grouping in the ListView.

>note Before proceeding, go through the [Grouping Overview]({%slug listview-features-grouping%}) topic.

1. Create the following business object:

 ```C#
public class City
{
    public string Continent { get; set; }
    public string Name { get; set; }
    public string Country { get; set; }
}
 ```

1. Create a `ViewModel` class as shown below:

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

1. To visualize the hierarchical relation between groups, add a custom `GroupHeaderTemplate` (of type `DataTemplate`) to the Resources of your page:

 ```XAML
<ResourceDictionary>
    <multiLevelGrouping:LevelToMarginConverter x:Key="LevelToMarginConverter" />
    <DataTemplate x:Key="ListViewItemTemplate">
        <telerikListView:ListViewTemplateCell>
            <telerikListView:ListViewTemplateCell.View>
                <Grid Padding="50, 0, 0, 0" BackgroundColor="#F1F2F5">
                    <Label Text="{Binding Name}" TextColor="#6F6F70" FontSize="Small" />
                </Grid>
            </telerikListView:ListViewTemplateCell.View>
        </telerikListView:ListViewTemplateCell>
    </DataTemplate>
    <DataTemplate x:Key="ListViewMultiLevelGroupHeaderTemplate">
        <Grid>
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="Auto" />
                <ColumnDefinition />
            </Grid.ColumnDefinitions>
            <Label Text="&#x25B8;" Margin="{Binding Level, Converter={StaticResource LevelToMarginConverter}}"
                   TextColor="DarkGray" FontSize="Medium">
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

1. The `LevelToMarginConverter` calculates the margin of each group header according to its Level:

 ```C#
public class LevelToMarginConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        if (value != null)
        {
            var level = (int)value;
            return new Thickness(((level - 1) * 20) + 8, 12, 0, 6);
        }
        else return value;
    }
    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        return value;
    }
}
 ```

1. Add the `RadListView` definition with two `PropertyGroupDescriptors` as shown in the next snippet:

 ```XAML
<telerikDataControls:RadListView x:Name="listView" ItemsSource="{Binding Cities}"
                                     ItemTemplate="{StaticResource ListViewItemTemplate}"
                                     GroupHeaderTemplate="{StaticResource ListViewMultiLevelGroupHeaderTemplate}"
                                     GroupHeaderStyle="{StaticResource ListViewGroupHeaderStyle}">
    <telerikDataControls:RadListView.BindingContext>
        <local:GroupingViewModel/>
    </telerikDataControls:RadListView.BindingContext>
    <telerikDataControls:RadListView.GroupDescriptors>
        <telerikListView:PropertyGroupDescriptor PropertyName="Continent"/>
        <telerikListView:PropertyGroupDescriptor PropertyName="Country"/>
    </telerikDataControls:RadListView.GroupDescriptors>
</telerikDataControls:RadListView>
 ```

1. Add the namespaces:

 ```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
 ```


The following image shows the final result.

![](../images/listview_grouping_multilevel.png)

## See Also

- [Grouping]({%slug listview-features-grouping%})
- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
