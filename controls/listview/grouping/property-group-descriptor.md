---
title: Property Group Descriptor
page_title: .NET MAUI ListView Documentation - Porperty Group Descriptors
description: Try now the Telerik UI for .NET MAUI ListView option PropertyGroupDescriptor for grouping items by a property value from the class that defines them.
position: 1
slug: listview-property-group-descriptor
previous_url: /controls/listview/grouping/listview-property-group-descriptor
tags: group, radlistview, groupdescriptor
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# .NET MAUI ListView Property Group Descriptor

You can group the data by a property value from the class that defines your items. This descriptor exposes the following properties:

- `PropertyName`&mdash;Defines the string name of the property you want to group by.
- `SortOrder`&mdash;Defines the sort order in each group to Ascending or Descending.

**1.** Add the following business object:

<snippet id='listview-grouping-groupdescriptors-businessobject' />

**2.** Add a `ViewModel` with a collection of Cities:

<snippet id='listview-grouping-groupdescriptors-viewmodel' />

**3.** Group the Cities by the `Country` property through the `PropertyGroupDescriptor`:

<snippet id='listview-grouping-propertygroupdescriptor'/>

**4.** Add the `Templates` definition in the page resources:

<snippet id='listview-grouping-templates' />

**5.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

> For the ListView PropertyGroupDescriptor example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ListView  -> Grouping category.

## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
