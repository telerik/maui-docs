---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Overview
description: Try out the best-in-class .NET MAUI DataGrid control with out-of-the-box support for operations like sorting, filtering and grouping, editing and more.
position: 0
previous_url: /controls/datagrid/datagrid-overview
slug: datagrid-overview
---

# .NET MAUI DataGrid Overview

The Telerik UI for .NET MAUI DataGrid is a powerful control that allows you to easily visualize and edit tabular represented data in your .NET MAUI applications. Most of the data on the Internet is stored in tables within a database. **Telerik UI for .NET MAUI DataGrid** provides the same abstraction over the data&mdash;it has columns and rows, and the intersection of a row and a column is called a cell. When the data from a database is sent to the client, it is usually converted to a Business object (or the so-called `ViewModel`) where each instance represents a table row and each property of the object represents a column within the original table.

![DataGrid Overview](images/datagrid-overview.png "Telerik .NET MAUI DataGrid")

## Key Features of the Telerik .NET MAUI Grid

* [Different column types]({%slug datagrid-columns-overview %})&mdash;The DataGrid provides plenty of built-in columns such as Text, Boolean, Numeric, ComboBox, Date, Time, and Template. These predefined templates allow you to handle different data types and user scenarios, each with its specific editor.

* [Load on demand]({%slug datagrid-features-loadondemand %})&mdash;In some cases, you may need to load data in the .NET MAUI DataGrid when the control is already displayed as this can improve the performance of your application. The DataGrid offers automatic data loading once the user scrolls to the last available record, or by displaying a customizable button which will initiate the loading of more data items.

* [Commands]({%slug datagrid-commands-overview %})&mdash;The DataGrid allows you to attach commands, such as `ColumnHeaderTap`, `CellTap`, `BeginEdit`, and more, which will be executed when certain actions occur.

* UI Virtualization&mdash;The highly optimized data layer of the DataGrid enables fast grouping, sorting, and filtering operations. The user interface uses virtualization for its row and cell elements, which means that visual elements are created only when needed and only for the currently visible cells.

* [Editing]({%slug datagrid-editing %})&mdash;You can enable users to edit the data presented in the .NET MAUI DataGrid. Depending on the column data type, a relevant editor allows end users to edit content in a friendly environment. For example, if one of the columns is a date, a date-picker will be used to offer a change in the date field.

* [Sorting]({%slug datagrid-sorting-overview %}), [filtering]({%slug datagrid-filtering-overview%}), and [grouping]({%slug datagrid-grouping-overview %})&mdash;You can easily perform SORT, FILTER, and GROUP operations on your data by using the convenient API of the control.

* [Selection modes]({%slug datagrid-selection-overview %})&mdash;The DataGrid features a single or a multiple-item selection and provides options for controlling the cell or row selection unit, thus enabling any selection scenario you want your MAUI application users to have.

* [Footer support]({%slug datagrid-column-footer%}) For datagrid columns.

* Rows alternation&mdash;The DataGrid supports alternating row colors so that your users can easily distinguish one row from another.

* [Row height]({%slug datagrid-row-height%})&mdash;Manually set the grid row height apply row height to control over the way the content is accommodated inside the grid cells.

* [Flexible styling API]({%slug datagrid-styling%})&mdash;The .NET MAUI DataGrid is highly customizable if you prefer to use your own styling.

## Next Steps

- [Getting Started with Telerik UI for .NET MAUI DataGrid]({% slug datagrid-getting-started %})


## See Also

- [.NET MAUI DataGrid product page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataGrid forum page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)


