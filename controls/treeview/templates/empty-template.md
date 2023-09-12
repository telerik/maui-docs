---
title: Empty Template
page_title: .NET MAUI TreeView Documentation - Empty Template
description: Learn more about the Empty Template property of the .NET MAUI TreeView control.
position: 2
slug: treeview-empty-template
---

# Empty Template

The TreeView control provides the ability to specify a template when the `ItemsSource` is null or the collection is empty.

It exposes the following properties:

* `EmptyTemplate`(`DataTemplate`)&mdash;Defines the content of the view which is shown when the view has no items.
* `EmptyStyle`(`Style` with target type `telerik:ItemsEmptyView`)&mdash;Specifies the style applied to the empty view. For more details, review the [TreeView Styling]({%slug treeview-style-overview%}#styling-the-empty-template) article.

**Example with Empty Template definition**

```XAML
<telerik:RadTreeView x:Name="treeView"
                        ItemsSource="{Binding Countries}">
    <telerik:TreeViewDescriptor TargetType="{x:Type local:Country}"
                                DisplayMemberPath="Name"
                                ItemsSourcePath="Cities" />
    <telerik:TreeViewDescriptor TargetType="{x:Type local:City}">
        <telerik:TreeViewDescriptor.ItemTemplate>
            <DataTemplate>
                <Label Text="{Binding Name}"
                        FontAttributes="Italic" />
            </DataTemplate>
        </telerik:TreeViewDescriptor.ItemTemplate>
    </telerik:TreeViewDescriptor>
    <telerik:RadTreeView.EmptyTemplate>
        <DataTemplate>
            <Label Text="No data"/>
        </DataTemplate>
    </telerik:RadTreeView.EmptyTemplate>
</telerik:RadTreeView>
```

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `Country` class:

<snippet id='treeview-country-model' />

**4.** Add the `ViewModel` class:

<snippet id='treeview-location-viewmodel' />

## See Also

* [Expand and Collapse TreeView Items]({%slug treeview-expand-collapse%})
* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})