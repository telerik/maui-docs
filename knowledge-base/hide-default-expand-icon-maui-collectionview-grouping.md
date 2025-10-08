---
title: Hiding Default Expand Icon in .NET MAUI CollectionView with Grouping
description: Learn how to hide the default expand icon in .NET MAUI CollectionView when grouping is used and use a custom icon instead.
type: how-to
page_title: Customizing Expand Icon in .NET MAUI CollectionView Grouping
meta_title: Customizing Expand Icon in .NET MAUI CollectionView Grouping
slug: hide-default-expand-icon-maui-collectionview-grouping
tags: collectionview, expand-collapse-indicator, grouping, header-template, styling
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 
## Description

I want to hide the default expand/collapse icon in the .NET MAUI CollectionView when grouping is used. I plan to use a custom icon and style it further.

This knowledge base article also answers the following questions:
- How can I replace the default expand icon in .NET MAUI CollectionView with a custom one?
- How to hide the expand/collapse indicator in .NET MAUI CollectionView grouping?
- How to style the expand/collapse icon in .NET MAUI CollectionView?

## Solution

To hide the default expand/collapse icon and use a custom icon, follow one of the options below:

### Option 1: Using `GroupViewStyle`

1. Remove the default expand arrow from the group template.
2. Use the `GroupViewStyle` property and its `ExpandCollapseIndicatorStyle` to style the expand indicator.

```XAML
<telerik:RadCollectionView.GroupViewStyle>
    <telerik:GroupViewStyle ExpandCollapseIndicatorStyle="{StaticResource ExpandCollapseIndicatorStyle}" />
</telerik:RadCollectionView.GroupViewStyle>
```

3. Define the style with the target type `Label`.

```XAML
<Style x:Key="ExpandCollapseIndicatorStyle" TargetType="Label">
    <Setter Property="TextColor" Value="Black" />
    <Setter Property="FontSize" Value="18" />
</Style>
```

Refer to the official documentation for more information on [GroupViewStyle](https://www.telerik.com/maui-ui/documentation/controls/collectionview/styling/group-style).

### Option 2: Removing Default Indicator

1. Set the `IsVisible` property of the expand/collapse indicator to `False` in the style.

```XAML
<Style x:Key="ExpandCollapseIndicatorStyle" TargetType="Label">
    <Setter Property="TextColor" Value="Black" />
    <Setter Property="IsVisible" Value="False" />
</Style>
```

2. Define your custom indicator in the group template.

```XAML
<telerik:RadCollectionView.GroupViewStyle>
    <telerik:GroupViewStyle ExpandCollapseIndicatorStyle="{StaticResource ExpandCollapseIndicatorStyle}" />
</telerik:RadCollectionView.GroupViewStyle>
```

## See Also

- [Grouping in CollectionView](https://www.telerik.com/maui-ui/documentation/controls/collectionview/grouping/overview)
- [CollectionView GroupViewStyle](https://www.telerik.com/maui-ui/documentation/controls/collectionview/styling/group-style)
- [Customizing Group Header Text Area](https://www.telerik.com/maui-ui/documentation/controls/collectionview/grouping/header#customizing-the-area-with-the-group-header-text)
