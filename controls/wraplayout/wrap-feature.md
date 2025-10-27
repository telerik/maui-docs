---
title: Wrap Functionality
page_title: .NET MAUI WrapLayout Documentation - Wrap Functionality
description: Lear how to set orientation, item sizing and position to the items in the Telerik .NET MAUI WrapLayout control. 
position: 2
previous_url: /controls/wraplayout/wraplayout-wrap-feature
slug: wraplayout-wrap-feature
---

# .NET MAUI Wrap Functionality for WrapLayout control

The WrapLayout is a layout container that lets you position items in rows or columns based on the `Orientation` property. When the space is filled, the container automatically wraps items onto a new row or column.

## Orientation

The WrapLayout exposes the `Orientation` property, which specifies whether the child items will be wrapped in rows (horizontal orientation) or in columns (vertical orientation). By default, the WrapLayout wraps its items horizontally.

The following example demonstrates how to set both the `"Horizontal"` and `"Vertical"` orientation:

<snippet id='wraplayout-orientation' />

And the resources for `RadBorder` and Label

<snippet id='wraplayout-orientation-resources' />

In the example, `telerik` is defined like this:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

The following image shows the end result on different platforms:

![.NET MAUI WrapLayout Orientation](images/wraplayout_orientation.png)

## Item Size

The WrapLayout exposes the `ItemWidth` and `ItemHeight` properties, which define the layout area for each child element. By default, the available size for the items is not restricted.

Here is a quick sample of a WrapLayout with a specified item size:

<snippet id='wraplayout-item-size' />

The following image shows the end result.

![.NET MAUI WrapLayout Item Size](images/wraplayout_itemsize.gif)

## Positioning the Last Child Element

The WrapLayout exposes the `StretchLastChild` property, which enables you to control the position and layout of the last child item from the layout items collection. If set to `True`, the last element will stretch along the remaining space from the last row or column depending on the layout orientation.

The following example shows how `StretchLastChild` will work when set to both values:

<snippet id='wraplayout-position-lastelement' />

The following image shows the end result.

![.NET MAUI WrapLayout Positioning](images/wraplayout_positionlast.png)

## See Also

- [Getting Started with Telerik UI for .NET MAUI WrapLayout]({% slug wraplayout-getting-started%})
