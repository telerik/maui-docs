---
title: Hiding Empty Group Headers in CollectionView for .NET MAUI
description: Learn how to hide group headers with empty or null keys in CollectionView for .NET MAUI, ensuring they do not occupy vertical space.
type: how-to
page_title: How to Hide Empty or Null Group Headers in .NET MAUI CollectionView
slug: hide-empty-group-headers-collectionview-net-maui
tags: collectionview, .net maui, group header, visibility, styling
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In scenarios where the CollectionView in .NET MAUI utilizes grouping, there might be groups with an empty string or null as their key. The goal is to completely hide such group headers so that they do not take up any vertical space in the UI. 

This knowledge base article also answers the following questions:

- How do I hide group headers with no content in CollectionView for .NET MAUI?
- Can I remove the space occupied by empty group headers in CollectionView?
- What is the way to conditionally display group headers based on their content in .NET MAUI CollectionView?

## Solution

To hide group headers in CollectionView for .NET MAUI when the group key is either an empty string or null and ensure they do not occupy space, use a combination of the `IsVisible` and `MinimumHeightRequest` properties within a `DataTrigger`. Apply these properties in the `Style` targeted at `RadCollectionViewGroupView`. Setting `MinimumHeightRequest` to `0` alongside making the group header invisible allows for the removal of the unwanted space that would otherwise be occupied by the header.

Here is how you can define the `Style` in your `ContentPage.Resources`:

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style TargetType="telerik:RadCollectionViewGroupView" x:Key="CollectionViewGroupStyle">
            <Style.Triggers>
                <DataTrigger TargetType="telerik:RadCollectionViewGroupView" Binding="{Binding Key}" Value="">
                    <Setter Property="IsVisible" Value="False" />
                    <Setter Property="MinimumHeightRequest" Value="0" />
                </DataTrigger>
            </Style.Triggers>
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
```

By implementing this solution, group headers with empty or null keys will be effectively hidden, and the vertical space they would typically occupy will be eliminated, resulting in a cleaner and more efficient UI presentation.

## See Also
- [CollectionView Overview in Telerik UI for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/collectionview/overview)
