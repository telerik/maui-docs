---
title: Changing HeaderText in TabView When Tab Item Is Selected
description: Learn how to dynamically change the HeaderText of TabView items when a tab is selected in UI for .NET MAUI.
type: how-to
page_title: Dynamically Update TabView HeaderText Based on Selection in UI for .NET MAUI
meta_title: Dynamically Update TabView HeaderText Based on Selection
slug: dynamically-update-tabview-headertext-based-on-selection
tags: tabview,selectionchanged,event,headertext,ui-for-net-maui
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | TabView for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)|

## Description

I need to change the `HeaderText` of the TabView items when they are selected. For example, when the "Home" tab is selected, its header should change to "Using Home". Similarly, when selecting "Function A", the header should change to "Applying Function A", and so on.

This knowledge base article also answers the following questions:
- How can I change the header text of TabView dynamically?
- How to update TabView `HeaderText` based on selection in .NET MAUI?
- How to use ``SelectionChanged` event in TabView to modify `HeaderText`?

## Solution

Use the [SelectionChanged](https://docs.telerik.com/devtools/maui/controls/tabview/selection#events) event of the TabView to dynamically update the header text based on the selected tab item.

1. Subscribe to the `SelectionChanged` event in the TabView.

```xaml
<telerik:RadTabView x:Name="tabView"
                    SelectionChanged="TabView_SelectionChanged">
    <telerik:TabViewItem HeaderText="Home"/>
    <telerik:TabViewItem HeaderText="Function A"/>
    <telerik:TabViewItem HeaderText="Function B"/>
    <telerik:TabViewItem HeaderText="Function C"/>
</telerik:RadTabView>
```

2. Implement a method to update the `HeaderText` dynamically based on the selected index. Handle the `SelectionChanged` event in the code-behind:

```csharp
private void TabView_SelectionChanged(object sender, EventArgs e)
{
    var headers = new[] { "Home", "Function A", "Function B", "Function C" };
    for (int i = 0; i < this.tabView.Items.Count; i++)
    {
        if (this.tabView.Items[i] is TabViewItem item)
        {
            item.HeaderText = headers[i];
        }
    }

    int selectedIndex = this.tabView.SelectedIndex;
    if (this.tabView.Items[selectedIndex] is TabViewItem selectedItem)
    {
        switch (selectedIndex)
        {
            case 0:
                selectedItem.HeaderText = "Using Home";
                break;
            case 1:
                selectedItem.HeaderText = "Applying Function A";
                break;
            case 2:
                selectedItem.HeaderText = "Applying Function B";
                break;
            case 3:
                selectedItem.HeaderText = "Applying Function C";
                break;
        }
    }
}
```

## See Also

- [TabView Overview](https://docs.telerik.com/devtools/maui/controls/tabview/overview)
- [SelectionChanged Event Documentation](https://docs.telerik.com/devtools/maui/controls/tabview/selection#events)
