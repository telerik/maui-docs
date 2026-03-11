---
title: Item Styles
page_title: .NET MAUI ListView Documentation - Item Styles
description: Check the Telerik for .NET MAUI ListView styling options for the ListViewItemStyle object.
position: 0
slug: listview-features-styling
previous_url: /controls/listview/styling/listview-features-styling
tags: style, selected, hovered, pressed, item, highlighted
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# .NET MAUI ListView Item Styles

The ListView component provides styling mechanism for customizing the look of its items.

This mechanism consists of the following properties of type `ListViewItemStyle`:

* `ItemStyle`
* `SelectedItemStyle`
* `PressedItemStyle`
* `ReorderItemStyle`

## ListViewItemStyle

The properties of this object are respectively applied to the native components. The supported ones are the following:

* `BackgroundColor` (`Color`)&mdash;Sets the background of the item(s).
* `BorderColor` (`Color`)&mdash;Sets the color of the border.
* `BorderWidth` (`double`)&mdash;Defines the width of the borer.
* `BorderLocation` (`Location`)&mdash;Describes an enumeration describing where the border will be visible.
* `TextCellTextColor` (`Color`)&mdash;Defines the text color of the ListView `TextCell`.

### Location

This enumeration contains the following members:

- `None`&mdash;The border will not be visualized.
- `Top`&mdash;The border will be visualized only at the top side.
- `Bottom`&mdash;The border will be visualized only at the bottom side.
- `Left`&mdash;The border will be visualized only at the left side.
- `Right`&mdash;The border will be visualized only at the right side.
- (Default) `All`&mdash;The border will be visualized all around the item.

## See Also

- [Selection]({%slug listview-features-selection%})
- [Reordering]({%slug listview-features-reorder-items%})
- [StyleSelector]({%slug listview-features-style-selector%})
