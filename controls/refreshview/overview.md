---
title: Overview
meta_title: .NET MAUI RefreshView Documentation - Overview
description: Discover the Telerik UI for .NET MAUI RefreshView, which adds pull-to-refresh to any content with built-in indicators, templates, and commands.
components: ["refreshview"]
tags: refreshview for .net maui, .net maui, ui for .net maui, microsoft .net maui, pull to refresh
position: 0
slug: refreshview-overview
---

# .NET MAUI RefreshView Overview

The Telerik UI for .NET MAUI RefreshView is a container control that adds pull-to-refresh behavior to any content. Use the RefreshView when users need to reload data on demand, for example, to update a news feed, a list of messages, or a data grid with server data.

The `RadRefreshView` wraps a single content view. When the user pulls the content past a configurable distance and releases it, the RefreshView starts a refresh. The RefreshView raises events and executes a command so that you can load fresh data, and then you end the refresh by setting `IsRefreshing` to `false`.

![.NET MAUI RefreshView with a circular refresh indicator displayed above a list of customers while the content is pulled down from the top edge](images/refreshview-overview.png)

## Key Features of the Telerik .NET MAUI RefreshView

The RefreshView provides the following features:

* [Refresh State]({% slug refreshview-refresh-state %})&mdash;Start and stop a refresh programmatically and turn the pull gesture on or off.
* [Indicator Type]({% slug refreshview-indicator-type %})&mdash;Choose between the built-in `Circular`, `Spinner`, and `Arrow` refresh indicators.
* [Pull Direction]({% slug refreshview-pull-direction %})&mdash;Start a refresh by pulling from the top, bottom, left, or right edge of the content.
* [Transition Mode]({% slug refreshview-transition-mode %})&mdash;Define how the indicator and the content move while the user pulls.
* [Thresholds]({% slug refreshview-thresholds %})&mdash;Control the pull distance at which the indicator appears and at which a refresh starts, and the indicator length.
* [Templates]({% slug refreshview-templates %})&mdash;Replace the built-in indicator with custom content for the pulling and refreshing phases.
* [Integration with CollectionView]({% slug refreshview-collectionview %})&mdash;Add pull-to-refresh to the Telerik CollectionView.
* [Integration with DataGrid]({% slug refreshview-datagrid %})&mdash;Add pull-to-refresh to the Telerik DataGrid.
* [Commands]({% slug refreshview-commands %})&mdash;Execute a view model command when a refresh starts.
* [Events]({% slug refreshview-events %})&mdash;Track the pull progress, cancel a pull gesture, and respond when a refresh starts or completes.
* [Styling]({% slug refreshview-styling %})&mdash;Customize the color, size, and shadow of the built-in indicators.

## Next Steps

- [Getting Started with the .NET MAUI RefreshView]({% slug refreshview-getting-started %})

## See Also

- [.NET MAUI RefreshView Forum Page](https://www.telerik.com/forums/maui)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
