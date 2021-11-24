---
title: Overview
page_title: .NET MAUI DataGrid Documentation | Overview
description: Check our &quot;Overview&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 0
slug: datagrid-overview
---

# Overview

Most of the data on the Internet is stored in tables within a database. **Telerik UI for .NET MAUI DataGrid** provides the same abstraction over the data&mdash;it has columns and rows, and the intersection of a row and a column is called a cell. When the data from a database is sent to the client, it is usually converted to a Business object (or the so-called `ViewModel`) where each instance represents a table row and each property of the object represents a column within the original table.

Currently, the Telerik UI for .NET MAUI DataGrid is available for Android and iOS.

![Overview DataGrid](images/overview-grid-1.png)

## Key Features

* [Different column types]({%slug datagrid-columns-overview %})&mdash;The DataGrid provides plenty of built-in columns such as Text, Boolean, Numeric, ComboBox, DateTime, and Template. These predefined templates allow you to handle different data types and user scenarios, each with its specific editor.

* [Load on demand]({%slug datagrid-features-loadondemand %})&mdash;In some cases, you may need to load data in the DataGrid when the control is already displayed as this can improve the performance of your application. The DataGrid offers automatic data loading once the user scrolls to the last available record, or by displaying a customizable button which will initiate the loading of more data items.

* [Commands]({%slug datagrid-commands-overview %})&mdash;The DataGrid allows you to attach commands, such as `ColumnHeaderTap`, `CellTap`, `BeginEdit`, and more, which will be executed when certain actions occur.

* UI Virtualization&mdash;The highly optimized data layer of the DataGrid enables fast grouping, sorting, and filtering operations. The user interface uses virtualization for its row and cell elements, which means that visual elements are created only when needed and only for the currently visible cells.

* [Editing]({%slug datagrid-editing %})&mdash;You can enable users to edit the data presented in the DataGrid. Depending on the column data type, a relevant editor allows end users to edit content in a friendly environment. For example, if one of the columns is a date, a date-picker will be used to offer a change in the date field.

* [Sorting]({%slug datagrid-sorting-overview %}), [filtering]({%slug datagrid-filtering-overview%}), and [grouping]({%slug datagrid-grouping-overview %})&mdash;You can easily perform SORT, FILTER, and GROUP operations on your data by using the convenient API of the control.

* [Selection modes]({%slug datagrid-selection-overview %})&mdash;The DataGrid features a single or a multiple-item selection and provides options for controlling the cell or row selection unit, thus enabling any selection scenario you want your MAUI application users to have.

* Rows alternation&mdash;The DataGrid supports alternating row colors so that your users can easily distinguish one row from another.

* [Flexible styling API]({%slug datagrid-styling%})&mdash;The DataGrid is highly customizable if you prefer to use your own styling.

## See Also

- [Getting Started with Telerik UI for .NET MAUI DataGrid]({% slug datagrid-getting-started %})
