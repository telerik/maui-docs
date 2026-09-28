---
title: Command
page_title: .NET MAUI DataGrid Documentation - Load On Demand Command
description: Learn how to load data on demand in the Telerik UI for .NET MAUI DataGrid by using the LoadMoreData command.
components: ["datagrid"]
position: 3
slug: datagrid-load-on-demand-command
tags: loading data, .net maui, maui, datagrid, load data on demand, loadmoredata command
---

# .NET MAUI DataGrid LoadMoreData Command

The `LoadMoreData` command is another alternative for loading data on demand. This alternative is suitable for MVVM scenarios.

## Example

The following example demonstrates a sample setup that shows how to use the command:

1. Define the DataGrid in XAML:

<snippet id='datagrid-customloadmoredatacommand-xaml'/>

2. Add the telerik namespace:

```xaml
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

2. Add sample data:

<snippet id='person-datamodel'/>

3. Define the `ViewModel`:

<snippet id='datagrid-customloadmoredatacommand-viewmodel-csharp'/>

4. Create the custom command:

<snippet id='datagrid-customloadmoredatacommand-csharp'/>

>important Invoking the `ShowLoadOnDemandLoadingIndicator` and `HideLoadOnDemandLoadingIndicators` methods is required. Without calling these methods, the `BusyIndicator` used for the functionality is not visualized.

5. Add the custom command to the `Commands` collection of the DataGrid:

<snippet id='datagrid-customloadmoredatacommand-addtocollection-csharp'/>

>important For DataGrid LoadMoreData command example, refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and go to the **DataGrid > LoadOnDemand** category.

## See Also

- [Load On Demand Overview]({%slug datagrid-features-loadondemand%})
- [Load On Demand Collection]({%slug datagrid-load-on-demand-collection%})
- [Load On Demand Event]({%slug datagrid-load-on-demand-event%})
- [Load On Demand Styling]({%slug datagrid-load-on-demand-styling%})
- [DataGrid Commands]({%slug datagrid-commands-overview%})
