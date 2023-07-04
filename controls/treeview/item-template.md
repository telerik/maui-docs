---
title: Item Template
page_title: .NET MAUI TreeView Documentation - Item Template
description: Review how to customize the default text displayed in the Telerik .NET MAUI TreeView control by using the item template. 
position: 7
slug: treeview-item-template
---

# .NET MAUI TreeView Item Template

Customize the text displayed in the Treeview item by using the `ItemTemplate` property. The `ItemTemplate` applies on TreeView level. The `ItemTemplate` does not include the checkbox, image and expand/collapse indicator. These elements are part of the `ControlTemplate`. For more details about how to customize the Treeview Control Template review the Control Template article. 

Here is an example how to define custom `ItemTemplate`: 

**1.** Define the `RadTreeView` control and the `ItemTemplate`: 

```XAML
<telerik:RadTreeView x:Name="treeView" 
                        ItemsSource="{Binding Items}">
    <telerik:TreeViewDescriptor ItemsSourcePath="Children"
                                DisplayMemberPath="Name"
                                TargetType="{x:Type local:Item}" />
    <!-- modify the label and add additional elements in the label area.
ItemTemplate does not include expand indicator, image, checkbox, only the text, you can add additional elements to it.
    For example, I have added a button-->
    <telerik:RadTreeView.ItemTemplate>
        <DataTemplate>
            <Grid ColumnDefinitions="*,auto">
                <Label Text="{Binding Name}" BackgroundColor="Yellow"/>
                <telerik:TreeViewItemButton Text="Button" Grid.Column="1" WidthRequest="100" BackgroundColor="Green" HorizontalOptions="End"/>
            </Grid>
        </DataTemplate>
    </telerik:RadTreeView.ItemTemplate>
</telerik:RadTreeView>
```

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `Item` class:

<snippet id='treeview-getting-started-item' />

**4.** Add the `ViewModel` class:

<snippet id='treeview-getting-started-viewmodel' />


## See Also

* [Expand and Collapse TreeView Items]({%slug treeview-expand-collapse%})
* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})
