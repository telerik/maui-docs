---
title: Migrating from Xamarin
page_title: Migrating the TreeView from Xamarin.Forms to .NET MAUI
description: "Learn how to migrate the Telerik UI for Xamarin TreeView to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages. "
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms, treeview
slug: migrate-xamarin-treeview-to-maui
position: 20
---

# Migrating the TreeView from Xamarin to .NET MAUI

Overall, Telerik .NET MAUI TreeView control is a complete new control with new API and improvements.

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin TreeView | `RadTreeView` | xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.XamarinForms.DataControls" | using Telerik.XamarinForms.DataControls; |
| .NET MAUI TreeView | `RadTreeView` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | using Telerik.Maui.Controls; |


## Modifying the API

| Xamarin TreeView | .NET MAUI TreeView |
| ------------- | --------------- |
| - | `HorizontalScrollBarVisibility` |
| - | `HorizontalScrollBarLayoutMode` |
| - | `VerticalScrollBarVisibility` |
| - | `VerticalScrollBarLayoutMode` |
| `SelectedItems Collection`(read-only) | `SelectedItems Collection` |
| - | `SelectedItem` |
| - | `SelectionMode` - `None`, `Single`, `Multiple` |
| `CheckedItemsCollection`(read-only) | `CheckedItemsCollection` |
| `CheckBoxModes`- `None`, `Individual`, `Propagate` | `CheckBoxModes` - `None`,`Independent`,`Recursive` |
| `ItemTemplate` | - |
| `LoadOnDemand` | - |
| `ScrollItemIntoView()` | `ScrollTo()` |
| - | `ItemsSourceChanged` event |
| `SelectionChanged` | `SelectionChanged` |
| `ItemTapped` event | `ItemTapped` event |
| `ItemHold` event | - |
| `ItemCollapsed` event | - |
| `ItemExpanded` event | - |
| Commands - `ItemTap`, `ItemHold`, `ItemCollapse`,`ItemExpand`,`LoadOnDemand`,`Unknown` | - |
| - | `ExpandAll` command |
| - | `CollapseAll` command |
| - | `CheckAll` command |
| - | `UnCheckAll` command |
| - | `ScrollToCommand` command |
| `ExpandAll()` | `ExpandAll()` |
| `ExpandAll()` | `CollapseAll()` |
| `Expand()` | - |
| `Collapse()` | - |
| - | `CheckAlll()` |
| - | `UnCheckAll()` |
| `CheckItem()` | - |
| `UncheckItem()` | - |


## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI TreeView Product Page](https://www.telerik.com/maui-ui/treeview)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
