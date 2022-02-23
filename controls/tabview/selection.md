---
title: Selection
page_title: .NET MAUI TabView Documentation | Selection
description: Check the Selection options for the Telerik TabView for .NET MAUI control.
slug: tabview-selection
tags: tabview, selection, selected item, .net maui
position: 0
---

# Selection

**Telerik TabView for .NET MAUI** exposes properties that help you work with the item selection: 

* `SelectedItem`(of type `Telerik.Maui.Controls.TabViewItem`)&mdash; set the selected item.
* `TabViewItem` can be selected by setting its `IsSelected`(`bool`) property to `True`.

**Example with SelectedItem**

<snippet id='tabview-features-selection-csharp'/>

And the namespace used:

```C#
using Telerik.Maui.Controls;
```

**Example with IsSelected**

```XAML
<telerik:RadTabView x:Name="tabView">
    <telerik:TabViewItem HeaderText="Home" IsSelected="True">
        <Label Margin="10" Text="This is the content of the Home tab" />
    </telerik:TabViewItem>
    <telerik:TabViewItem HeaderText="Folder">
        <Label Margin="10" Text="This is the content of the Folder tab" />
    </telerik:TabViewItem>
    <telerik:TabViewItem HeaderText="View">
        <Label Margin="10" Text="This is the content of the View tab" />
    </telerik:TabViewItem>
</telerik:RadTabView>
```

And the namespace used:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

## Events

* `SelectionChanged` event which is raised when the currently selected `TabViewItem` has changed. The `SelectionChanged` event handler receives two parameters: 
	* The `Sender` which is of type `Telerik.Maui.Controls.RadTabView`.
	* and `EventArgs`.

## Next Steps

- [Getting Started with Telerik UI for .NET MAUI TabView]({%slug tabview-getting-started%})
