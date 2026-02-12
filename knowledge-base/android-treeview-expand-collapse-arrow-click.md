---
title: Restricting Expand/Collapse to Arrow Click in UI for .NET MAUI TreeView on Android and iOS
description: Learn how to configure the UI for .NET MAUI TreeView to expand/collapse items only when clicking the arrow on Android and on iOS.
type: how-to
page_title: Configure UI for .NET MAUI TreeView Expand/Collapse on Arrow Click for Android
meta_title: Configure UI for .NET MAUI TreeView Expand/Collapse on Arrow Click for Android
slug: android-treeview-expand-collapse-arrow-click
tags: treeview, ui-for-net-maui, itemtapped-event, expand-collapse
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 12.1.0 | Telerik UI for .NET MAUI TreeView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to configure the [UI for .NET MAUI TreeView](https://www.telerik.com/maui-ui/documentation/controls/treeview/expand-collapse) so that items only expand or collapse when clicking the arrow. Currently, on Android, the items expand or collapse when clicking anywhere on the item. This behavior is different from WinUI and MacCatalyst, where items expand or collapse only when clicking the arrow.

This knowledge base article also answers the following questions:
- How to disable item tap for expand/collapse in UI for .NET MAUI TreeView on Android and iOS?
- How to limit expand/collapse to arrow click in UI for .NET MAUI TreeView?
- How to handle ItemTapped events in UI for .NET MAUI TreeView?

## Solution

To restrict the expand/collapse behavior to only the arrow click in Android, handle the `RadTreeView.ItemTapped` event and set `e.Handled` to `true`. This prevents the default behavior of expanding or collapsing the item when tapping on the text.

```csharp
private void treeView_ItemTapped(object sender, Telerik.Maui.Controls.ItemsView.ItemViewTappedEventArgs e)
{
    e.Handled = true; // Prevents expand/collapse on text tap
}
```

## See Also

- [UI for .NET MAUI TreeView Documentation](https://www.telerik.com/maui-ui/documentation/controls/treeview/overview)
- [Expand/Collapse Behavior in UI for .NET MAUI TreeView](https://www.telerik.com/maui-ui/documentation/controls/treeview/expand-collapse)
- [Handling Events in UI for .NET MAUI TreeView](https://www.telerik.com/maui-ui/documentation/controls/treeview/events)
