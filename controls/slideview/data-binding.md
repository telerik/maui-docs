---
title: Data Binding
page_title: .NET MAUI SlideView Documentation - Data Binding
description: Review the data binding and virtualization options for the NET MAUI SlideView control.
position: 3
slug: slideview-data-binding
---

# .NET MAUI SlideView Data Binding and Virtualization Options

The Telerik UI for .NET MAUI SlideView provides UI virtualization and an option to bind data.

## Binding to a Complex Object

To define the collection of the items that will populate the control with data, use `ItemsSource`(`IEnumerable`).

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

## Virtualization Mode

UI virtualization is a technique used to generate visual containers only for the visible part of the control (the viewport).
For example, if the data items collection contains 100 records, but the size of the control allows to show only 20 at once, only 20 containers will be generated. When the viewport changes, the number of generated containers may increase or decrease based on the available size.

The Telerik UI for .NET MAUI SlideView control uses UI virtualization on demand. So the creation and preparation of the views is delayed until an item gets near the viewport. You can disable the virtualization, by setting the `VirtualizationMode` (`enum` of type `Telerik.Maui.Controls.SlideView.VirtualizationMode`) property to `None`. The default value is `LoadOnDemand`.

Here is a sample SlideView definition with a `VirtualizationMode` set to `None`:

```XAML
<telerik:RadSlideView x:Name="slideView"
                        ItemsSource="{Binding Views}" 
                        VirtualizationMode="None"/>
```

## See Also

- [Item Template]({%slug slideview-item-template%}) 
- [Control Template]({%slug slideview-control-template%})
