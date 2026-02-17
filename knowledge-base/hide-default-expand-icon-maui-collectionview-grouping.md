---
title: Hiding Default Expand Icon in .NET MAUI CollectionView with Grouping
description: Learn how to hide the default expand icon in .NET MAUI CollectionView when grouping is used and use a custom icon instead.
type: how-to
page_title: Customizing Expand Icon in .NET MAUI CollectionView Grouping
meta_title: Customizing Expand Icon in .NET MAUI CollectionView Grouping
slug: hide-default-expand-icon-maui-collectionview-grouping
tags: collectionview, expand-indicator, grouping, group-template, styling, hide expand icon
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 13.0.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)|

## Description

I want to hide the default expand icon in the .NET MAUI CollectionView when grouping is used. I plan to use a custom icon and style it further.

This knowledge base article also answers the following questions:
- How can I replace the default expand icon in .NET MAUI CollectionView with a custom one?
- How to hide the expand indicator in .NET MAUI CollectionView grouping?
- How to style the expand icon in .NET MAUI CollectionView?

## Solution

Use the following steps to customize or hide the expand icon in the .NET MAUI CollectionView when grouping is enabled.

* [Customize the Expand Icon in .NET MAUI CollectionView Grouping](#customize-the-expand-icon)
* [Hide the Expand Icon in .NET MAUI CollectionView Grouping](#hide-the-expand-icon)

### Customize the Expand Icon

To use a custom expand icon in the .NET MAUI CollectionView when grouping is enabled, you have to use the `GroupViewStyle` property:

```XAML
<telerik:RadCollectionView>
    <telerik:RadCollectionView.GroupViewStyle>
        <Style TargetType="telerik:RadCollectionViewGroupView">
            <Setter Property="ExpandCollapseIndicatorStyle" Value="{StaticResource ExpandCollapseIndicatorStyle}" />
        </Style>
    </telerik:RadCollectionView.GroupViewStyle>
</telerik:RadCollectionView>
```

Define the `ExpandCollapseIndicatorStyle` style to customize the expand icon. You can set a custom icon or change the text color, for example:

```XAML
<ContentPage.Resources>
    <ResourceDictionary>
        <Style x:Key="ExpandCollapseIndicatorStyle" TargetType="Label">
            <Setter Property="TextColor" Value="Red" />
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
```

### Hide the Expand Icon

To hide the expand icon set the `IsVisible` property of the expand indicator to `False` in the `ExpandCollapseIndicatorStyle`:

```XAML
<ContentPage.Resources>
    <ResourceDictionary>
        <Style x:Key="ExpandCollapseIndicatorStyle" TargetType="Label">
            <Setter Property="TextColor" Value="Black" />
            <Setter Property="IsVisible" Value="False" />
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
```

Then set the `ExpandCollapseIndicatorStyle` to the `GroupViewStyle` of the CollectionView as shown below:

```XAML
<telerik:RadCollectionView>
    <telerik:RadCollectionView.GroupViewStyle>
        <Style TargetType="telerik:RadCollectionViewGroupView">
            <Setter Property="ExpandCollapseIndicatorStyle" Value="{StaticResource ExpandCollapseIndicatorStyle}" />
        </Style>
    </telerik:RadCollectionView.GroupViewStyle>
</telerik:RadCollectionView>
```

## See Also

- [Grouping in CollectionView](https://www.telerik.com/maui-ui/documentation/controls/collectionview/grouping/overview)
- [CollectionView GroupViewStyle](https://www.telerik.com/maui-ui/documentation/controls/collectionview/styling/group-style)
- [Customizing Group Header Text Area](https://www.telerik.com/maui-ui/documentation/controls/collectionview/grouping/header#customizing-the-area-with-the-group-header-text)
