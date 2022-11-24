---
title: ItemStyle Selector
page_title: .NET MAUI ListView Documentation - ItemStyle Selector
description: Check our &quot;ItemStyle Selector&quot; documentation article for Telerik ListView for .NET MAUI.
position: 1
previous_url: /controls/listview/styling/listview-features-style-selector
slug: listview-features-style-selector
---

# .NET MAUI ListView ItemStyle Selector

The ListView component exposes conditional styling feature. It allows users to apply a different `Style` to each item depending on a specific condition.

## Example

The following example will demonstrate how to apply the `Conditional Styling` in the ListView control. 

1. Set up the ListView control:

 <snippet id='listview-styleselector-listview-xaml'/>

1. Create a simple data for the ListView component:

 <snippet id='listview-styleselector-source'/>

1. You can set a different style for a specific item by using the `ListViewStyleSelector` class. We can use the `OnSelectStyle` method to change the styles of the items in the ListView control. A sample implementation of a custom class that derives from `ListViewStyleSelector` and overrides its `OnSelectStyle` method is shown below:

 <snippet id='listview-features-onselectstyle'/>

The following image shows how the ListView control will look like when conditional styling is used.

![ListView StyleSelector](../images/listview-features-style-selector.png "Style Selector")

> For ItemStyle Selector example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ListView -> Styling category.

## See Also

- [Selection]({%slug listview-features-selection%})
- [Styling]({%slug listview-features-styling%})
- [Reordering]({%slug listview-features-reorder-items%})
