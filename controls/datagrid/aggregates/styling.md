---
title: Aggregate Styling
page_title: .NET MAUI DataGrid Documentation - Aggregate Styling
description: "Review the Telerik .NET MAUI DataGrid Aggregates Styling documentation article to learn more about all built in Aggregate Styling functions you can use."
position: 0
slug: datagrid-aggregates-styling
---

# DataGrid Aggregates Styling

The DataGrid Aggregate component provides styling mechanism customizing the look of the DataGrid Column Footer, the Group Footer and Group Header.

The styling mechanism is represented by the following properties:

* `GroupHeaderStyle`(`DataGridGroupHeaderStyle`)&mdash;Defines the style of the `GroupHeader` and the aggregates inside the header.
* `GroupFooterStyle`(`DataGridGroupFooterStyle`)&mdash;Defines the style of the `GroupFooter` and the aggregates inside the footer.
* `GroupFooterStyleSelector`(`DataGridStyleSelector`)&mdash; Defines the style of the selected GroupFooter by passing the `GroupFooterContext` in the selector.
* `FooterStyle`(`DataGridColumnFooterStyle`)&mdash;Defines the style of the Column Footer and the aggregates inside the Column Footer. 

> In order to visualize the GroupFooter the `ShowGroupFooters` needs to be set to `True`.

> To visualize the GroupHeader Aggregates the `ShowGroupHeaderAggregates` property needs to be set to `True`.

## GroupFooterStyle 

The following example shows how to define the GroupFooterStyle in XAML:

<snippet id='datagrid-group-aggregate-styling-example'/>

## GroupFooterStyleSelector

The following example shows how to use the `GroupFooterStyleSelector` property.

Define the class to which the `GroupFooterContext` will be passed.

<snippet id='datagrid-group-aggregate-style-selector'/>

Define the style selector which will passed to the DataGrid in XAML.

<snippet id='datagrid-group-aggregate-style-selector-xaml'/>

The final result is as follows:

![Group Aggregate Style](../images/datagrid-grouping-aggregates.png)