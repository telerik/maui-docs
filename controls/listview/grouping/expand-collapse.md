---
title: Expand and Collapse Groups
page_title: .NET MAUI ListView Documentation | Expand and Collapse Groups
description: Check our &quot;Expand and Collapse Groups&quot; documentation article for Telerik ListView for .NET MAUI.
position: 3
slug: listview-features-expand-collapse
previous_url: /controls/listview/grouping/listview-features-expand-collapse
description: Describing RadListView grouping feature
tags: group, radlistview, expand, collapse, collapsible
---

# Expand and Collapse Groups

The ListView supports groups expand and collapse operations either through the UI by tapping on the group headers or programmatically. By default, all the groups are expanded.

This help topic will provide an overview of the methods and commands used to control the expand/collapse state of the ListView groups.

>tip Before proceeding, check the [Grouping]({%slug listview-features-grouping%}) topic which describes how to enable the grouping feature of ListView.

## Get the Grouped ListView Items

To manipulate the collapsible ListView groups, first you will need to call its `GetDataView` method. In short, GetDataView method provides a view of the ItemsSource after all the Sort, Group and Filter operations are applied. The return type is `IDataViewCollection` which exposes the expand and collapse methods described in the following sections.

```C#
var dataView = this.listView.GetDataView();
```

## Expand and Collapse All Groups

To expand all groups, use the `ExpandAll` method. To collapse all groups, use the `CollapseAll` method.

```C#
//expand all
var dataView = this.listView.GetDataView();
dataView.ExpandAll();

//collapse all
var dataView = this.listView.GetDataView();
dataView.CollapseAll();
```

## Expand and Collapse a Certain Group

You can retrieve the first-level groups through the `GetGroups` method of the `IDataViewCollection` object and use `ExpandGroup`/`CollapseGroup` to make a certain group to expand or collapse respectively. You can check whether a group is expanded trough the `GetIsExpanded` method.

Here is quick snippet on how these methods are used:

```C#
var dataView = this.listView.GetDataView();
var rootGroups = dataView.GetGroups();

var isFirstExpanded = dataView.GetIsExpanded(rootGroups.First());
//expand a certain group
dataView.ExpandGroup(rootGroups.First());
//collapse a certain group
dataView.CollapseGroup(rootGroups.First());
```

Additionally, `IDataViewCollection` provides the `ExpandItem`/`CollapseItem` methods that take a ListView item as a parameter and expand/collapse the immediate group containing this item.

```C#
var lastItem = (listView.ItemsSource as IEnumerable<City>).Last();
var dataView = this.listView.GetDataView();
dataView.CollapseItem(lastItem);
```

## Handle the GroupHeaderTap Command

The `GroupHeaderTap` command is raised when a group header of a grouped ListView is tapped. By default, tapping on a group header collapses the group if it is expanded and vice-versa.

By handling the `GroupHeaderTap` command, you can control the collapse/expand behavior of a certain group. The next example shows how to prevent the first-level groups from hiding their items.

>tip For more information on using the ListVew commands, refer to the [Commands]({%slug listview-features-commands%}) topic.

First, let’s define the `GroupHeaderTapCommand` class that derives from `ListViewCommand`:

```C#
	public class GroupHeaderTapCommand : ListViewCommand
	{
		public GroupHeaderTapCommand()
		{
			Id = CommandId.GroupHeaderTap;
		}
		public override bool CanExecute(object parameter)
		{
			return true;
		}
		public override void Execute(object parameter)
		{
			var context = parameter as GroupHeaderContext;
			if (context.Level > 1)
				context.IsExpanded = !context.IsExpanded;
		}
	}
```

Add the `GroupHeaderTapCommand` to the `Commands` collection of the ListView instance:

```C#
listView.Commands.Add(new GroupHeaderTapCommand());
```

## See Also

- [Grouping]({%slug listview-features-grouping%})
- [Commands]({%slug listview-features-commands %})
