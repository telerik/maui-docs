---
title: ItemTemplateSelector
page_title: .NET MAUI ListView Documentation - ItemTemplateSelector
description: Learn more about the Item Template Selector property of the Telerik UI for .NET MAUI ListView control.
position: 3
previous_url: /controls/listview/cells/listview-itemtemplateselector
slug: listview-item-template-selector
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# .NET MAUI ListView ItemTemplateSelector

The ListView control exposes an `ItemTemplateSelector` property which you can use to apply different template to each item depending on a specific condition.  

This article will show you how you can use this property to achieve divergent appearance for the different items within your Telerik UI for .NET MAUI ListView control.

## Template Selector Implementation

You have a `RadListView` bound to a collection of multiple `DataItem` objects and the appearance of each item depends on a specific property of the business object. 

**1.** Add the `DataItem` class:

<snippet id='listview-itemtemplateselector-dataitem' />

**2.** Create a sample `ViewModel` class with a collection of `DataItem` objects. The collection will later be applied to the `ItemsSource` property of the ListView:

<snippet id='listview-itemtemplateselector-sourcecollection' />

**3.** You need to apply different template to the item based on the value of the `IsSpecial` property, you have to create a custom class that inherits from `DataTemplateSelector`. This class will return different `DataTemplate` according to whether the value is true or false:

<snippet id='listview-itemtemplateselector-customitemtemplateselector' />

**4.** Set this custom class as the `ItemTemplateSelector` property of the `RadListView` and customize the templates within it:

<snippet id='listview-itemtemplateselector-setting-itemtemplateselector' />

**5.** Add the needed namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"        
```

Running the sample will lead to the following appearance of the control:

![.NET MAUI ListView ItemTemplateSelector](../images/listview-itemtemplateselector.png)

## See Also

- [ListView Text Cell]({% slug listview-textcell %})
- [ListView Template Cell]({% slug listview-templatecell %})
- [Layouts]({% slug listview-features-layouts %})
- [Items Styling]({% slug listview-features-styling %})
