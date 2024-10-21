---
title: Removing Separator Lines in TreeView for .NET MAUI on Android and iOS
description: Learn how to remove the bottom border separator lines from TreeView items on both Android and iOS platforms in .NET MAUI applications.
type: how-to
page_title: How to Remove TreeView Items Separator Lines in .NET MAUI on Mobile Platforms
slug: remove-treeview-items-separator-lines-net-maui
tags: treeview, .net maui, android, ios, separator, border
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 | Telerik UI for .NET MAUI TreeVIew | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In a .NET MAUI application, each `TreeViewItem` on Android and iOS has a bottom border separator line as part of the `TreeViewItemView`. The need arises to remove this line for styling purposes. This KB article also answers the following questions:
- How to style the TreeView items in .NET MAUI for mobile platforms?
- How to remove the border from TreeView items on Android and iOS?
- How to customize the appearance of TreeView items in .NET MAUI?

## Solution

To remove the bottom border separator line from TreeView items on both Android and iOS platforms, set the `BorderColor` to `Transparent` and the `BorderThickness` to `0`. Apply the following style definition in your XAML:

```xml
<Style TargetType="telerik:TreeViewItemView">
    <Setter Property="BorderColor" Value="Transparent"/>
    <Setter Property="BorderThickness" Value="0"/>
</Style>
```

This style can be set either as an implicit style, which affects all TreeViewItemView elements within scope, or as an explicit style, which applies to the TreeView or to the `TreeViewItem` elements you assign it to.

## See Also

- [TreeView Overview]({%slug treeview-overview%})
- [Styling the .NET MAUI TreeView Item]({%slug treeview-item-style%})
