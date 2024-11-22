---
title: Data Binding
page_title: .NET MAUI SlideView Documentation - Data Binding
description: Review the data binding options for the NET MAUI SlideView control.
position: 3
slug: slideview-data-binding
---

# .NET MAUI SlideView Data Binding

The Telerik UI for .NET MAUI SlideView provides built-in options that allow you to bind data.

To define the collection of the items that will populate the control with data, use `ItemsSource`(`IEnumerable`).

## Binding to a Complex Object

**1.** Add the SlideView definition in XAML:

<snippet id='slideview-orientation-xaml'/>

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the sample Data Model and the View Model:

- Business Model

<snippet id='slideview-datamodel'/>

- View Model

<snippet id='slideview-events-viewmodel'/>

## See Also

- [Item Template]({%slug slideview-item-template%}) 
- [Control Template]({%slug slideview-control-template%})
