---
title: Overview
page_title: .NET MAUI ListView Documentation - Grouping
description: Check our &quot;Overview&quot; documentation article for Telerik ListView for .NET MAUI.
position: 0
slug: listview-features-grouping
previous_url: /controls/listview/grouping/listview-grouping
description: Describing RadListView grouping feature
tags: group, radlistview, groupdescriptor
---

# Grouping

The ListView provides you with the functionality to programmatically group its data at runtime. This can be achieved through adding groupdescriptors to the `RadListView.GroupDescriptors` collection.

* `PropertyGroupDescriptor`
* `DelegateGroupDescriptor`

## PropertyGroupDescriptor

You can group the data by a property value from the class that defines your items. For more details, refer to [Property Group Descriptor]({%slug listview-features-expand-collapse %}) article.

## DelegateGroupDescriptor

This descriptor enables you to group by a custom key (e.g. some complex expression combining two or more properties) instead of being limited by the value of a single property. For more details go to [Delegate Group Descriptor]({%slug listview-delegate-group-descriptor%}) article.

## Custom Group Header Template

Create custom `GroupHeaderTemplate` in order to achieve the desired look when grouping the ListView. For more details, refer to the [Group Header Template]({%slug listview-customize-group-header%}) article.

## Sticky Group Headers

The ListView provides the option to set its group headers as sticky. This means the GroupHeader will "freeze" while scrolling through the items until the whole group is scrolled away. As you scroll through the next group, the currently stuck group header will be pushed by the next group header.

For more information on how to enable the Sticky Group Header feature, refer to the [Sticky Group Headers]({%slug listview-sticky-group-header%}) article.

## Expand/Collapse Groups

The control supports groups expand and collapse operations either through the UI by tapping on the group headers or programmatically. For more details, refer to the [Expand and Collapse Groups]({%slug listview-features-expand-collapse %}) article.

## Bindable GroupDescriptor

Users can control the `GroupDescriptor` collection by using MVVM. For more details, refer to the [Bindable Group Descriptors]({%slug listview-bindable-group-descriptor%}) article.


## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
