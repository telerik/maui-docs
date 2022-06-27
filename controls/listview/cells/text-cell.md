---
title: TextCell
page_title: .NET MAUI ListView Documentation - TextCell
description: Check our &quot;Cell Types&quot; documentation article for Telerik ListView for .NET MAUI control.
position: 1
previous_url: /controls/listview/cells/listview-textcell
slug: listview-textcell
---

# TextCell

Cells in the ListView are the presentation of each data item from the control's ItemsSource. You can choose between the `ListViewTextCell` and `ListViewTemplateCell` cell types.

`ListViewTextCell` derives from `Xamarin.Forms.TextCell` and displays text. It can optionally render detail text as a second row within a list view item. This is the default cell of the ListView.

The example below demonstrates how to create a list view with text cells, like this:

![](../images/listview-celltypes-textcell.png)

Create a view model that will be the source of the list view:

<snippet id='listview-celltypes-textcell-viewmodel' />

Add the definition of the ListView control:

<snippet id='listview-celltypes-textcell-listview-xaml' />

Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [TemplateCell]({%slug listview-textcell%})
- [ItemTemplate Selector]({%slug listview-item-template-selector%})
- [Layouts]({% slug listview-features-layouts %})
- [Items Styling]({% slug listview-features-styling %})
