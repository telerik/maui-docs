---
title: Horizontal ListView in GridLayout
description: How to set horizontal orientation of ListView GridLayout definition
type: how-to
page_title: Create Horizontal ListView with GridLayout
slug: listview-horizontal-orientation--gridlayout
position: 
tags: listview, horizontal, grid layout, orientation, .net maui, .net, dotnet
ticketid: 1606449
res_type: kb
---

## Environment

| Product | Author | 
| --- | ---- | 
| Telerik UI for .NET MAUI ListView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 


## Description

This article described how to set the horizontal orientation of the ListView when GridLayout definition is used. 

## Solution

The RadListView has two type of layout definitions - `Linear` and `Grid`. Both definitions has `Orientation` property which allows you to set the layout orientation to `Horizontal` or `Vertical`. 

The default value of Orientation property is `Vertical`. If you want to apply horizontal orientation to Linear or Grid layout, set the property to `Horizontal`.

**ListViewGridLayout with Horizontal orientation:**

```XAML
<telerik:RadListView.LayoutDefinition>
    <telerik:ListViewGridLayout Orientation="Horizontal"/>
</telerik:RadListView.LayoutDefinition>
```

**ListViewGridLayout with Horizontal orientation:**

```XAML
<telerik:RadListView.LayoutDefinition>
	<telerik:ListViewGridLayout Orientation="Horizontal"/>
</telerik:RadListView.LayoutDefinition>
```

**ListViewLinearLayout with Horizontal orientation:**

```XAML
<telerik:RadListView.LayoutDefinition>
	<telerik:ListViewLinearLayout Orientation="Horizontal"/>
</telerik:RadListView.LayoutDefinition>
```

## See Also

-[ListView Layouts]({%slug listview-features-layouts%}})