---
title: Group Header Template
page_title: .NET MAUI ListView Documentation | Grouping
description: Check our &quot;Group Header Template&quot; documentation article for Telerik ListView for .NET MAUI.
position: 4
slug: listview-customize-group-header
previous_url: /controls/listview/grouping/listview-customize-group-header
description: Describing RadListView grouping feature
tags: group, radlistview, groupdescriptor, custom group header
---

# Group Header Template

The ListView has a default group header that is displayed when grouping is applied.

The `BindingContext` of the `GroupHeader` is a complex object and it includes the following properties:

- `IsExpanded`&mdash;Defines a value indicating whether the group is currently expanded (has its child items visible).
- `Items`&mdash;Gets the child items of the group.
- `Key`&mdash;Gets the specific for the group key.
- `Level`&mdash;Gets the zero-based level (or the depth) of the group.

In addition, you can create a custom `GroupHeaderTemplate` to achieve the desired look when grouping the ListView.

1. Define the `GroupHeaderTemplate`:

 ```XAML
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
        <Label Margin="0, 12, 0, 6" Text="{Binding Key}" Grid.Column="1" TextColor="DarkGray" FontSize="Medium" HorizontalOptions="Start" />
    </Grid>
</DataTemplate>
 ```

1. Set the template to the `RadListView`:

 ```XAML
<telerikDataControls:RadListView x:Name="listView" ItemsSource="{Binding Cities}"
                                     GroupHeaderTemplate="{StaticResource ListViewGroupHeaderTemplate}">
    <telerikDataControls:RadListView.BindingContext>
        <local:GroupingViewModel/>
    </telerikDataControls:RadListView.BindingContext>
    <telerikDataControls:RadListView.GroupDescriptors>
        <telerikListView:PropertyGroupDescriptor PropertyName="Country"/>
    </telerikDataControls:RadListView.GroupDescriptors>
</telerikDataControls:RadListView>
 ```



## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
