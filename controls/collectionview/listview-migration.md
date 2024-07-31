---
title: Migrating from Telerik .NET MAUI ListView to Telerik CollectionView
page_title: Migrating from Telerik .NET MAUI ListView to Telerik CollectionView
description: Learn how to migrate the Telerik UI for .NET MAUI ListView to the Telerik CollectionView for .NET MAUI.
slug: listview-migration
position: 22
---

# Migrating the Telerik .NET MAUI ListView to CollectionView

The Telerik UI for .NET MAUI CollectionView control has been designed and built as a new control which provides the same functionality as the Telerik .NET MAUI ListView control, but at the same introduces a slew of enhancements, aimed at resolving existing issues, boosting performance, and facilitating effortless customization. 

## API Differences

When migrating the Telerik .NET MAUI ListView, consider the following differences in the API:

| Telerik .NET MAUI ListView | Telerik .NET MAUI CollectionView |
| ------------- | ------------- |
| Presenting the data through cells - `ListViewTextCell`, `ListViewTemplateCell` | [Presenting the data]({%slug collectionview-data-binding%}) through a `DisplayMemberPath` property or by defining an `ItemTemplate` |
 Selection - `None`, `Single` or `Multiple`, provide an option to set selection gesture - `Tap`, `Hold` | [Selection]({%slug collectionview-selection%}) - `None`, `Single` or `Multiple`, no selection gesture |
| Grouping through `PropertyGroupDescriptor` or `DelegateGroupDescriptor`, methods for expanding/collapsing groups, multi-level grouping, sticky group headers | [Grouping]({%slug collectionview-grouping%}) through `PropertyGroupDescriptor` or `DelegateGroupDescriptor`, methods for expanding/collapsing groups, multi-level grouping, no sticky group headers |
| Sorting through `PropertySortDescriptor` or `DelegateSortDescriptor` | [Sorting]({%slug collectionview-sorting%}) through `PropertySortDescriptor` or `DelegateSortDescriptor` |
| Filltering through `DelegateFilterDescriptor` | [Filtering]({%slug collectionview-filtering%}) through various filter descriptors, such as `TextFilterDescriptor`, `NumericalFilterDescriptor`, etc |
| Header and Footer templates | [Header and Footer templates]({%slug collectionview-header-footer%}) |
| Load On Demand - Automatic and Manual, items can be loaded on demand through a `ListViewLoadOnDemandCollection`, a `LoadOnDemand` event or LoadOnDemand `ListViewUserCommand`  | Load On Demand - Automatic and Manual, items can be loaded on demand through a `LoadOnDemandCollection`, a `LoadOnDemand` event or `LoadOnDemandCommand` |
| Scrolling - `VerticalScrollBarVisibility` property, `ScrollItemIntoView` method | [Scrolling]({%slug collectionview-scrolling%}) - `ScrollItemIntoView` method, `Scrolled` event |
| Linear and Grid Layouts | [Linear]({%slug collectionview-linear-layout%}) and [Grid]({%slug collectionview-grid-layout%}) Layouts |
| Cell Swipe with `ItemSwipeContentTemplate` and `SwipeOffset` | [Item Swipe]({%slug collectionview-item-swipe-overview%}) with `StartSwipeTemplate`, `EndSwipeTemplate`, `StartSwipeLength` and `EndSwipeLength` properties |
| Pull To Refresh built-in funcionality | [Refresh Data functionality]({%slug collectionview-pull-to-refresh%}) through a RefreshView control |
| Reorder Items with `IsItemsReorderEnabled` property | [Drag and Drop feature]({%slug collectionview-dragdrop-overview%}) with `IsDragDropEnabled` property, customizable `DragDropBehavior` | 
| N/A | [Empty Template] feature through `EmptyContentTemplate` and `EmptyContentDisplayMode` |
| Events - `ItemTapped`, `ItemHold`, `GroupHeaderTapped` , `RefreshRequested`, `SelectionChanged` | [Events]({%slug collectionview-events%}) - `ItemTapped`, `GroupTapped`, `Scrolled`, `SelectionChanged` |
| Predefined commands through `CommandId` enumeration| [Commands]({%slug collectionview-commands%}) -  `ItemTapCommand`, `GroupTapCommand`, Item Swipe commands, LoadOnDemand commands |
| Styling - `ItemStyle`, `SelectedItemStyle`, `PressedItemStyle`, `ReorderItemStyle`, `ItemStyleSelector`, `GroupHeaderStyle` | [Styling]({%slug collectionview-item-styling%}) - `ItemViewStyle` with visual states, [DragVisual]({%slug collectionview-dragdrop-templates%}), `ItemViewStyleSelector`, `GroupViewStyle`, `GroupViewStyleSelector`|

## See Also

- [Data Binding]({%slug collectionview-data-binding%})
- [Drag & Drop]({%slug collectionview-dragdrop-overview%})
- [Item Swipe]({%slug collectionview-item-swipe-overview%})
- [Item Styling]({%slug collectionview-item-styling%})