---
title: Bindable GroupDescriptor
page_title: .NET MAUI ListView Documentation | Grouping
description: Check our &quot;Bindable GroupDescriptor&quot; documentation article for Telerik ListView for .NET MAUI.
position: 10
slug: listview-bindable-group-descriptor
previous_url: /controls/listview/grouping/listview-bindable-group-descriptor
description: Describing RadListView grouping feature
tags: group, radlistview, groupdescriptor
---

# Bindable GroupDescriptor

The GroupDescriptor collection now can be controlled by users using MVVM.

In order to control the GroupDescriptor collection through MVVM:

Create a property of type `ObservableCollection<GroupDescriptorBase>` in your `ViewModel` which will contain the needed group descriptors:

<snippet id='listview-features-bindable-groupdescriptor-viewmodel'/>

Use the `OneWayToSource` binding mode to bind that property to the `GroupDescriptors` property of `RadListView`:

<snippet id='listview-features-bindable-groupdescriptor-xaml' />
 
Here is how the `GroupDescriptor` collection looks like through MVVM:

![GroupDescriptorsMVVM](../images/listview-features-bindable-group.png)

> For the ListView Bindable GroupDescriptor example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ListView  -> Grouping category.

## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
