---
title: Selection
page_title: .NET MAUI TabView Documentation - Selection
description: Review the Selection options for the Telerik TabView for .NET MAUI control.
slug: tabview-selection
tags: tabview, selection, selected item, .net maui
position: 7
---

# Selection in .NET MAUI TabView

The Telerik TabView for .NET MAUI exposes properties that help you work with the item selection: 

## Selection through the UI

The `TabViewItem` can be selected through the UI by tapping on the header item. When tapping on the header item, the `SelectedIndex` and `SelectedItem` properties get updated.

## Programmatic Selection

You can programmatically select a `TabViewItem` by setting the following properties:

* `SelectedItem` (of type `Telerik.Maui.Controls.TabViewItem`)&mdash;Defines the selected item. The value of this property affects which header item is selected in the header area and which content is displayed in the content area.
* `SelectedIndex` (`int`)&mdash;Specifies the index of the currently selected `TabViewItem`. The value of this property affects which header item is selected in the header area and which content is displayed in the content area.

* `IsSelected` (`bool`)&mdash;Set the property directly to the `TabViewItem` to initiale a selection.

### Animation

* `AnimationEasing` (`Microsoft.Maui.Easing`)&mdash;Specifies the easing of the animation that is run when the value of the `SelectedIndex` property changes.
* `AnimationDuration` (`int`)&mdash;Specifies the duration in milliseconds of the animation that is run when the value of the `SelectedIndex` property changes.

**Example with Selected Item**

<snippet id='tabview-features-selection-csharp'/>

And the namespace used:

```C#
using Telerik.Maui.Controls;
```

**Example with `IsSelected`**

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
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

## Events

* `SelectionChanged` event which is raised when the currently selected `TabViewItem` has changed. The `SelectionChanged` event handler receives two parameters: 
	* The `Sender` which is of type `Telerik.Maui.Controls.RadTabView`.
	* and `EventArgs`.

## See Also

- [TabViewItem]({%slug tabview-item%})
- [Styling]({%slug tabview-styling%})
- [Templates]({%slug tabview-templates%})