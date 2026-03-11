---
title: Selection
page_title: .NET MAUI ListView Documentation - Selection
description: Learn more about the selection functionality about the Telerik UI for .NET MAUI ListView control.
position: 4
previous_url: /controls/listview/listview-features-selection
slug: listview-features-selection
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# .NET MAUI ListView Selection

The ListView component exposes selection feature. It allows single or multiple selection of the ListView items. This feature provides both visual and programmatic feedback for the actions of the user. Also you can disable the selection.

## Selection Mode

The ListView provides three selection modes, which allow you to manipulate the type of selection. This is controlled by the `SelectionMode` (`Telerik.Maui.Controls.Compatibility.DataControls.ListView.SelectionMode`) property which has the following entries:

- `None`&mdash;This mode doesn't allow users to select an item.
- `Single`&mdash;This is the default selection mode. It allows users to select only one item.
- `Multiple`&mdash;This mode allows users to select more than one item.

## Selection Gestures

You can also configure how the selection to be triggered by the end users through the `SelectionGesture` (`Telerik.Maui.Controls.Compatibility.DataControls.ListView.SelectionGesture`) property:

- `Tap`&mdash;Tap on an item to select it. This is the default `SelectionGesture` value.
- `Hold`&mdash;Tap and hold an item to select it.

## Selected Item

The ListView provides the `SelectedItem` (`object`) property, which specifies the last selected item of the ListView.

## Selected Items Collection

The ListView provides the `SelectedItems` (`ObservableCollection&lt;object&gt;`) property, which is a read-only collection used to get the currently selected items.

## Selection Events

The ListView provides the `SelectionChanged` event, which is triggered whenever the `SelectedItems` collection is changed. The `SelectionChanged` event handler receives two parameters:

* The sender argument which is of type object, but can be cast to the `RadListView` type.
* A `NotifyCollectionChangedEventArgs` object which provides information on the collection changed event. For more details, refer to the [NotifyCollectionChangedEventArgs Class](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.notifycollectionchangedeventargs) topic.

## Styling the Selected Item(s)

You can customize the way selected items look by applying `SelectedItemStyle` property to the `RadListView` instance. For detailed information on the approach, go to the [Items Styles]({%slug listview-features-styling%}) topic in ListView documentation.

## See Also

- [Items Grouping]({%slug listview-features-grouping%})
- [Items Sorting]({%slug listview-features-sorting%})
- [Items Styling]({%slug listview-features-styling%})
