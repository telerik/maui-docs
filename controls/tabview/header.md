---
title: Header
page_title: .NET MAUI TabView Documentation | Header
description: Review the header configuration options of the Telerik TabView for .NET MAUI control.
slug: tabview-header
tags: tabview, overview
position: 0
---

# Configuration

In this article we will review all configuration that the TabView control provides. 

## Setting the Header's Position

Use the `HeaderPosition`(enum of type`Telerik.Maui.Controls.TabViewHeaderPosition`)property of the RadTabView to control the position of the header. 

The available options are: `Top`, `Bottom`, `Left` and `Right`.

```XAML

```

## Spacing between the header and the content

* Apply spacing in pixels between the header area and the content area using the `HeaderSpacing`(`double`)property.

## Scrolling in the TabView header

TabView control allows you to scroll through the tabs inside the TabView Header. To enable the scrolling use the `IsHeaderScrollable`(`bool`)property. The default value is `True`.

## Overlaied header area

* `IsHeaderOverlaid`(`bool`)&mdashIndicates whether the header area is overlaid on top of the content area. 

When the `IsHeaderOverlaid` is set to `True`, the header area is centered and partially overlaps with one of the borders of the content area, based on the value of the `HeaderPosition` property. The padding of the content area is adjusted accordingly, to avoid overlapping with the header area.

When the `IsHeaderOverlaid` is set to `False`, the header area is placed adjacent to the content area without any overlapping, based on the value of the `HeaderPosition` property.

## Swiping inside the TabView content

Easily change the selected item using swipe gesture. This allows you to change the selected item of the TabView.

If you want to prevent this feature you will need to set the `IsContentSwipingEnabled`(`bool`) property to `False`. The default value is `True`.

## Styling

In order to apply styling to the TabView Header you need to use the following properties: 

* `HeaderStyle`(`Microsoft.Maui.Controls.Style`)&mdashSpecifies the style of the entire header area (border, background color etc.);
* `HeaderItemStyle`(`Microsoft.Maui.Controls.Style`)&mdashSpecifies the style of the individual header items (font, text color etc.)

## Templates

* `HeaderTemplate`(`Microsoft.Maui.Controls.ControlTemplate`)&mdash
* `ContentTemplate`(`Microsoft.Maui.Controls.ControlTemplate`)&mdash