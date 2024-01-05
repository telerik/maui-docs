---
title: Bindable GroupDescriptor
page_title: .NET MAUI CollectionView Documentation - Bindable Group Descriptors
description: Explore the Telerik UI for .NET MAUI CollectionView Bindable GroupDescriptor feature that lets you control the GroupDescriptor through MVVM.
position: 10
slug: collectionview-bindable-group-descriptor
tags: group, collectionview, groupdescriptor
---

# .NET MAUI CollectionView Bindable GroupDescriptor

Control the GroupDescriptor collection through MVVM

Create a property of type `ObservableCollection<GroupDescriptorBase>` in your `ViewModel` which will contain the needed group descriptors:

<snippet id='listview-features-bindable-groupdescriptor-viewmodel'/>

Use the `OneWayToSource` binding mode to bind that property to the `GroupDescriptors` property of `RadListView`:

<snippet id='listview-features-bindable-groupdescriptor-xaml' />
 
Here is how the `GroupDescriptor` collection looks like through MVVM:

![.NET MAUI CollectionView Group Descriptors MVVM]()

> For a runnable demo with the CollectionView Bindable Group Descriptors example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Grouping** category.

## See Also

