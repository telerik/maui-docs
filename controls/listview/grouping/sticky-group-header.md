---
title: Sticky Group Headers
page_title: .NET MAUI ListView Documentation - Sticky Group Grouping
description: Review the Telerik UI for .NET MAUI ListView Sticky Group Headers option which if enabled makes the GroupHeader freeze while scrolling through the items until the whole group is scrolled away.
position: 6
slug: listview-sticky-group-header
previous_url: /controls/listview/grouping/listview-sticky-group-header
tags: group, radlistview, groupdescriptor, sticky, group, headers
---

# .NET MAUI ListView Sticky Group Headers

The ListView provides the option to set its group headers as sticky. This means the `GroupHeader` will "freeze" while scrolling through the items until the whole group is scrolled away. As you scroll through the next group, the currently stuck group header will be pushed by the next group header.

To enable the sticky group headers behavior, set `IsGroupHeaderSticky` property of the ListView to `True`. By default `IsGroupHeaderSticky` value is `False`.

```XAML
<telerik:RadListView x:Name="listView"
                     IsGroupHeaderSticky="True"  />
```
```C#
var listView = new RadListView();
listView.IsGroupHeaderSticky = true;
```

The following image shows the sticky group headers in action:

![ListView Sticky Group Headers](../images/listview_stickyheaders.gif)

## See Also

- [Filtering]({%slug listview-features-filtering%})
- [Sorting]({%slug listview-features-sorting%})
- [Selection]({%slug listview-features-selection%})
