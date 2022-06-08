---
title: GroupHeader Style
page_title: .NET MAUI ListView Documentation | GroupHeader Style
description: Check our &quot;GroupHeader Style&quot; documentation article for Telerik ListView for .NET MAUI.
position: 2
slug: listview-styling-group-header
previous_url: /controls/listview/styling/listview-styling-group-header
description: Describing the styling options of the RadListView
tags: style, group, header
---

# GroupHeader Style

In addition to the [Item Styles]({%slug listview-features-styling%}), the ListView enables you to modify the visual appearance of its group headers when grouping is enabled. The feature is implemented through the `GroupHeaderStyle` property of type `ListViewGroupStyle`.

The `ListViewGroupStyle` provides means for customizing the border as well as background and text color of the group headers. Below you can find a list of the available styling options:

* `BackgroundColor` (`Color`)&mdash;Sets the background of the group header(s).
* `BorderColor` (`Color`)&mdash;Sets the color of the border.
* `BorderWidth` (`double`)&mdash;Defines the width of the borer.
* `BorderLocation` (`Location`)&mdash;Defines an enumeration describing where the border will be visible.
* `TextColor` (`Color`)&mdash;Defines the text color of the ListView `GroupHeader`.

>important To learn more about the grouping functionality of the ListView, refer to the [Grouping Overview]({%slug listview-features-grouping%}) topic.

### Example

1. Create a `City` class:

 <snippet id='listview-groupstyle-source'/>

1. Add a `ViewModel` class:

 <snippet id='listview-groupstyle-viewmodel'/>

1. Add the `RadListView` definition with a `GroupHeaderStyle` applied:

 <snippet id='listview-groupstyle-listview-xaml' />

The following image shows the end result:

![](../images/listview_styling_groupheader.png)

> For a GroupHeader Style example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ListView -> Styling category.

## See Also

- [Grouping]({%slug listview-features-grouping%})
- [Item Styles]({%slug listview-features-styling%})
- [Items StyleSelector]({%slug listview-features-style-selector%})
