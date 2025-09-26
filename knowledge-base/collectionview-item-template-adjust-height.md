---
title: Adjusting Item Template Height in CollectionView for .NET MAUI
description: Learn how to make the item template in CollectionView for .NET MAUI occupy only the space it uses by removing extra white space.
type: how-to
page_title: Removing Extra Space Below Text in CollectionView Item Template
meta_title: Removing Extra Space Below Text in CollectionView Item Template
slug: collectionview-item-template-adjust-height
tags: collectionview, .net maui, item template, minimumheightrequest, itemlength
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 


## Description

I want the item template of the CollectionView to only occupy the space it uses. The extra white space below the text in the item needs to be removed.

This knowledge base article also answers the following questions:  
- How can I adjust the height of CollectionView items dynamically?  
- How can I remove the default minimum height set for CollectionView items?  
- How can I improve performance with fixed item heights in .NET MAUI CollectionView?  

## Solution

To control the height of the item template in CollectionView for .NET MAUI and remove extra white space, follow one of the solutions below:



### Setting a Fixed Height with `ItemLength`

Use the `ItemLength` property of the [`CollectionViewLinearLayout`](https://docs.telerik.com/devtools/maui/controls/collectionview/layouts/linear-layout) to explicitly define the height of the items. If the item size is static, this improves the control's virtualization performance.

```XAML
<telerik:RadCollectionView.ItemsLayout>
    <telerik:CollectionViewLinearLayout ItemLength="20"/>
</telerik:RadCollectionView.ItemsLayout>
```

### Adjusting `MinimumHeightRequest` for Dynamic Sizing

To enable dynamic sizing, set the `MinimumHeightRequest` of the `RadCollectionViewItemView` to 0 using the `ItemViewStyle`:

```XAML
<telerik:RadCollectionView.ItemViewStyle>
    <Style TargetType="telerik:RadCollectionViewItemView">
        <Setter Property="MinimumHeightRequest" Value="0" />
    </Style>
</telerik:RadCollectionView.ItemViewStyle>
```

## See Also

- [CollectionView Documentation](https://docs.telerik.com/devtools/maui/controls/collectionview/overview)
- [CollectionViewLinearLayout Overview](https://docs.telerik.com/devtools/maui/controls/collectionview/layouts/linear-layout)
