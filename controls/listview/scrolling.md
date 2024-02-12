---
title: Scrolling
page_title: .NET MAUI ListView Documentation - Scrolling
description: Try now the Telerik UI for .NET MAUI ListView Scrolling options like the Vertical Scrollbar and programmatic scrolling with the ScrollItemIntoView method.
position: 10
slug: listview-features-scrolling
previous_url: /controls/listview/listview-features-scrolling
tags: programmatic, scrolling
---

# .NET MAUI ListView Scrolling

The ListView supports a number of options which define its scrolling behavior.

## Vertical ScrollBar

You can set the visibility of ListView vertical scrollbar according to your preferences with the `VerticalScrollBarVisibility` property. `VerticalScrollBarVisibility` (`Microsoft.Maui.ScrollBarVisibility`) specifies whether the vertical scrollbar will be visualized. By default, the property is `ScrollBarVisibility.Default` which means the scrollbar behavior depends on the target platform.

Here is a quick snippet on how you can set it to `ScrollBarVisibility.Always`:

```XAML
<telerikDataControls:RadListView x:Name="listView"
                                 VerticalScrollBarVisibility="Always" />
```
```C#
var listView = new RadListView();
listView.VerticalScrollBarVisibility = ScrollBarVisibility.Always;
```

## Programmatic Scrolling

The ListView exposes the `ScrollItemIntoView(object item)` method for programmatic scrolling to a specific data item. `ScrollItemIntoView` attempts to bring the specified data item into the view.

The following example demonstrates how to use `ScrollItemIntoView` inside a button click event handler.

**1.** Define a sample view with a ListView control and a button:

<snippet id='listview-features-programmatic-scrolling-xaml'/>

**2.** Use the following `ViewModel` to create a simple data for the ListView component:

<snippet id='listview-features-programmatic-scrolling'/>

**3.** Create the button click event handler and inside this method use `ScrollItemIntoView` to navigate to a specific item:

<snippet id='listview-features-programmatic-scrolling-scroll-to-item-method'/>

The following image shows the end result:

![.NET MAUI ListView Programmatic Scrolling](images/listview-features-scrolling.png)

## See Also

- [Selection]({%slug listview-features-selection%})
- [Grouping]({%slug listview-features-grouping%})
- [Reordering]({%slug listview-features-reorder-items%})
