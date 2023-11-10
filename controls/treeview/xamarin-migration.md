---
title: Migrating from Xamarin
page_title: Migrating the TreeView from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin TreeView to the Telerik UI for .NET MAUI framework by updating the namespacesby updating the namespaces, the incompatible NuGet packages and API.
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms, treeview
position: 100
slug: migrate-xamarin-treeview-to-maui
position: 20
---

# Migrating the TreeView from Xamarin.Forms to .NET MAUI

The Telerik UI for .NET MAUI TreeView control has been designed and built from the ground up as a new control with a new API and significant improvements over its Xamarin counterpart.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms TreeView and .NET MAUI TreeView.

## Namespaces Differences

When migrating the TreeView from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin TreeView | `RadTreeView` | xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.XamarinForms.DataControls" | using Telerik.XamarinForms.DataControls; |
| .NET MAUI TreeView | `RadTreeView` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | using Telerik.Maui.Controls; |

## API Differences

When migrating the TreeView from Xamarin to .NET MAUI, consider the following differences in the API:

| Xamarin TreeView | .NET MAUI TreeView |
| ------------- | --------------- |
| N/A | `HorizontalScrollBarVisibility` |
| N/A | `HorizontalScrollBarLayoutMode` |
| N/A | `VerticalScrollBarVisibility` |
| N/A | `VerticalScrollBarLayoutMode` |
| `SelectedItems Collection`(read-only) | `SelectedItems Collection` |
| N/A | `SelectedItem` |
| N/A | `SelectionMode` - `None`, `Single`, `Multiple` |
| `CheckedItemsCollection`(read-only) | `CheckedItemsCollection` |
| `CheckBoxModes`- `None`, `Individual` (independent), `Propagate` (recursive) | `CheckBoxModes` - `None`,`Independent`,`Recursive` |
| `ItemTemplate` (applies on TreeViewDescriptor level) | `ItemTemplate` (applies on TreeView level), `ItemTemplate` (applies on TreeViewDescriptor level) |
| `ScrollItemIntoView()` | `ScrollTo()` |
| N/A | `ItemsSourceChanged` event |
| `SelectionChanged` | `SelectionChanged` event |
| `ItemTapped` event | `ItemTapped` event |
| `ItemHold` event | `ItemHolding` event |
| `ItemCollapsed` event | `ItemCollapsed` event |
| `ItemExpanded` event | `ItemExpanded` event |
| N/A | `ItemChecked` event |
| N/A | `ItemUnchecked` event |
| N/A | `LoadChildrenOnDemand` event |
| `ItemTap` command | `ItemTappedCommand` |
| `ItemHold` command | `ItemHoldingCommand` | 
| `ItemCollapse` command | `ItemCollapsedCommand` |
| `ItemExpand` command | `ItemExpandedCommand` |
| `LoadOnDemand` command | `LoadChildrenOnDemandCommand` |
| N/A | `ExpandAllCommand` |
| N/A | `CollapseAllCommand` |
| N/A | `ExpandCommand` |
| N/A | `CollapseCommand` |
| N/A | `CheckAllCommand` |
| N/A | `UncheckAllCommand` |
| N/A | `UncheckCommand` |
| N/A | `CheckCommand` |
| N/A | `ScrollToCommand` |
| N/A | `ItemCheckedCommand` |
| N/A | `ItemUncheckedCommand` |
| `ExpandAll()` | `ExpandAll()` |
| `ExpandAll()` | `CollapseAll()` |
| `Expand()` | `Expand()` |
| `Collapse()` | `Collapse()` |
| N/A | `CheckAlll()` |
| N/A | `UnCheckAll()` |
| `CheckItem()` | `Check()` |
| `UncheckItem()` | `Uncheck()` |
| `ItemStyle` (applies on TreeView level) | `ItemStyle` (applies on TreeView level), `ItemStyle` (applies on TreeViewDescriptor level) |
| `ItemStyleSelector` (applies on TreeView level) | `ItemStyleSelector` (applies on TreeView level), `ItemStyleSelector` (applies on TreeViewDescriptor level) |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI TreeView Product Page](https://www.telerik.com/maui-ui/treeview)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
