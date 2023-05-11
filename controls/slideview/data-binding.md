---
title: Data Binding
page_title: .NET MAUI SlideView Documentation - Data Binding
description: "Review the data binding oprions for .NET MAUI SlideView control."
position: 4
slug: slideview-data-binding
---

# .NET MAUI SlideView Data Binding

- `ItemsSource`(`IEnumerable`)&mdash;Defines the collection of the items that will populate the control with data.

## Binding to a complex object

Here is the SlideView definition in XAML:

<snippet id='slideview-getting-started-complex-object-xaml'/>

In addition to this, you need to add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

the sample business model

<snippet id='slideview-businessmodel'/>

and the ViewModel used:

<snippet id='slideview-viewmodel'/>

## See Also

- [Item Template]({%slug slideview-item-template%}) 
- [Control Template]({%slug slideview-control-template%})
