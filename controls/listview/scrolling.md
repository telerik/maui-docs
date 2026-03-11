---
title: Scrolling
page_title: .NET MAUI ListView Documentation - Scrolling
description: Try now the Telerik UI for .NET MAUI ListView Scrolling options like the Vertical Scrollbar and programmatic scrolling with the ScrollItemIntoView method.
position: 10
slug: listview-features-scrolling
previous_url: /controls/listview/listview-features-scrolling
tags: programmatic, scrolling
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# .NET MAUI ListView Scrolling

The ListView supports a number of options which define its scrolling behavior.

## Vertical ScrollBar

You can set the visibility of ListView vertical scrollbar according to your preferences with the `VerticalScrollBarVisibility` property. `VerticalScrollBarVisibility` (`Microsoft.Maui.ScrollBarVisibility`) specifies whether the vertical scrollbar will be visualized. By default, the property is `ScrollBarVisibility.Default` which means the scrollbar behavior depends on the target platform.

## Programmatic Scrolling

The ListView exposes the `ScrollItemIntoView(object item)` method for programmatic scrolling to a specific data item. `ScrollItemIntoView` attempts to bring the specified data item into the view.

## See Also

- [Selection]({%slug listview-features-selection%})
- [Grouping]({%slug listview-features-grouping%})
- [Reordering]({%slug listview-features-reorder-items%})
