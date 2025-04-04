---
title: Handling Selection Changes in TabView for .NET MAUI
description: Learn how to determine the selected tab in RadTabView for .NET MAUI and perform actions based on the selected tab.
type: how-to
page_title: How to Handle Selection Changes in TabView for .NET MAUI
slug: tabview-net-maui-handle-selection-changes
tags: tabview, .net maui, selectionchanged, event, selectedindex, selecteditem
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | Telerik UI for .NET MAUI TabView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When using the TabView in a .NET MAUI application, it's common to perform different actions based on the user's selection of a tab. To facilitate this, you need to know how to determine which tab has been selected when the `SelectionChanged` event is triggered. 

This knowledge base article also answers the following questions:
- How can I perform actions based on the selected tab in RadTabView?
- How to access the selected tab's index or item in RadTabView?
- What is the best way to handle tab selection changes in a .NET MAUI app?

## Solution

To determine the selected tab in `RadTabView` and perform specific actions based on that, you need to handle the `SelectionChanged` event. In the event handler, you can access the `SelectedIndex` or `SelectedItem` properties to identify the selected tab. Here's how to implement the `SelectionChanged` event handler:

1. First, ensure you have the `SelectionChanged` event hooked up to your `RadTabView` in your XAML or code-behind.
2. Implement the event handler method in your code-behind as follows:

```csharp
private void TabView_OnSelectionChanged(object? sender, EventArgs e)
{
    // Cast the sender to RadTabView to access its properties
    var tabView = sender as Telerik.Maui.Controls.RadTabView;

    if (tabView != null)
    {
        // Access the selected tab's index if required
        var selectedTabIndex = tabView.SelectedIndex;

        // Access the selected tab item directly if required
        var selectedTabItem = tabView.SelectedItem as TabViewItem;

        // Perform actions based on the selected tab's index or the tab item itself
    }
}
```

This event demonstrates how to check the selected tab by accessing the `SelectedIndex` for the index or `SelectedItem` for the tab item directly. You can then use these values to perform your specific actions depending on the tab that is clicked.

## See Also

- [TabView Overview](https://docs.telerik.com/devtools/maui/controls/tabview/overview)
- [Handling Events in RadTabView](https://docs.telerik.com/devtools/maui/controls/tabview/selection)
