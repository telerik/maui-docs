---
title: Events
page_title: .NET MAUI DataGrid Documentation | Events
description: Check our &quot;Events&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 9
slug: datagrid-events-overview
description: Describing the events of the RadDataGrid
tags: events
---

# Events

The DataGrid component exposes a set of events.

## Load On Demand Events

* `LoadOnDemand`&mdash; Occurs when the load on demand is requested

## Disctinct Values Events

* `DistinctValuesLoading`&mdash;Occurs when loading the distinct values that will be displayed in the `Telerik.Maui.Controls.Compatibility.DataGrid.DataGridDistinctValuesFilterView`.

## Data Binding

* `DataBindingComplete`&mdash; Occurs when the associated DataGrid data(`ItemsSource`) has been successfully bound to the control or any data operation like Group, Sort or filter is applied.

## Selection Change

* `SelectionChanged`&mdash; Occurs when the currently selected items change.

## Example

The following example demonstrates the usage of the `LoadOnDemand` event&mdash;

Define the LoadOnDemand method in XAML:

<snippet id ="datagrid-loadondemand-event-xaml"/>

Create the method defining the functionality of the event:

<snippet id="datagrid-loadondemand-event-csharp"/>

## See Also

 - [Filtering]({%slug datagrid-filtering-overview%})
 - [Grouping]({%slug datagrid-grouping-overview%})
 - [Selection]({%slug datagrid-selection-overview%})
 - [Load On Demand]({%slug datagrid-features-loadondemand%})
 - [Sorting]({%slug datagrid-sorting-overview%})
 - [Row Height]({%slug datagrid-row-height%})
 - [Editing]({%slug datagrid-editing%})
