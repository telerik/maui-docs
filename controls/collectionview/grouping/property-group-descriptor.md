---
title: Property Group Descriptor
page_title: .NET MAUI CollectionView Documentation - Porperty Group Descriptors
description: Try now the Telerik UI for .NET MAUI CollectionView option PropertyGroupDescriptor for grouping items by a property value from the class that defines them.
position: 1
slug: collectionview-property-group-descriptor
tags: group, collectionview, groupdescriptor
---

# .NET MAUI CollectionView Property Group Descriptor

You can group the data by a property value from the class that defines your items. The `CollectionViewPropertyGroupDescriptor` exposes the following properties:

- `PropertyName`&mdash;Defines the string name of the property you want to group by.
- `SortOrder`(enum of type `Telerik.Maui.Controls.CollectionView.CollectionViewSortOrder`)&mdash;Specifies the sort order of the grouped items. The available options are: `Ascending` or `Descending`.

Add the following business object:

<snippet id='listview-grouping-groupdescriptors-businessobject' />

Add a `ViewModel` with a collection of Cities:

<snippet id='listview-grouping-groupdescriptors-viewmodel' />

Group the Cities by the `Country` property through the `PropertyGroupDescriptor`:

<snippet id='listview-grouping-propertygroupdescriptor'/>

Add the `Templates` definition in the page resources:

<snippet id='listview-grouping-templates' />

Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

> For a runnable demo with the CollectionView PropertyGroupDescriptor example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Grouping** category.

## See Also

