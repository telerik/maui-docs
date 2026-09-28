---
title: Styling
page_title: .NET MAUI DataGrid Documentation - Load On Demand Styling
description: Learn how to style the loading indicator and the Load More row of the Telerik UI for .NET MAUI DataGrid load-on-demand feature.
components: ["datagrid"]
position: 4
slug: datagrid-load-on-demand-styling
tags: loading data, .net maui, maui, datagrid, load data on demand, styling, template
---

# .NET MAUI DataGrid Load On Demand Styling

The DataGrid exposes several mechanisms for styling the load-on-demand functionality, which you can use according to the `LoadOnDemandMode` you have chosen.

## Style the Loading Indicator in Automatic Mode

### Style the Default Loading Indicator

A loading indicator is visualized when data is loaded on demand automatically. The indicator is a [`RadBusyIndicator`]({%slug busyindicator-overview%}), so to style its appearance, use an implicit style with `TargetType` set to `telerik:RadBusyIndicator`:

```XAML
<Style TargetType="telerik:RadBusyIndicator">
    <Setter Property="AnimationContentWidthRequest" Value="80" />
    <Setter Property="AnimationContentHeightRequest" Value="100" />
    <Setter Property="AnimationContentColor" Value="LightBlue" />
    <Setter Property="AnimationType" Value="Animation5" />
    <Setter Property="BackgroundColor" Value="LightCoral" />
</Style>
```

### Define Custom Loading Template

The `LoadOnDemandAutoTemplate` (`DataTemplate`) property allows you to define a custom template for the loading indicator when the `LoadOnDemandMode` is set to `Automatic`.

1. Define the custom template in XAML:

<snippet id='datagrid-loadondemandautotemplate-xaml'/>

2. Set the template to the `LoadOnDemandAutoTemplate` property of the DataGrid:

<snippet id='datagrid-setting-loadondemandautotemplate-xaml'/>

>important For DataGrid LoadOnDemand AutoTemplate example, refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and go to the **DataGrid > LoadOnDemand** category.

## Style the Loading Indicator in Manual Mode

### Style the LoadMore Row

Use the `LoadOnDemandRowStyle` property to style the appearance of the row that contains the **Load More** button when the `LoadOnDemandMode` is `Manual`.

1. The custom style is of type `Style` with target type `DataGridLoadOnDemandRowAppearance`:

<snippet id='datagrid-loadondemandrowstyle-xaml'/>

2. Set the style to the `LoadOnDemandRowStyle` property of the DataGrid:

<snippet id='datagrid-setting-loadondemandrowstyle-xaml'/>

The following image shows the row appearance after setting the `LoadOnDemandRowStyle` property:

![Telerik UI for .NET MAUI DataGrid load on demand row with a customized Load More button style](../images/datagrid-rowstyle.png)

>important For DataGrid LoadMore Row styling example, refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and go to the **DataGrid > LoadOnDemand** category.

### Customize the LoadMore RowTemplate

Use the `LoadOnDemandRowTemplate` property to set the template of the row that contains the **Load More** button when the `LoadOnDemandMode` is `Manual`.

1. The following example demonstrates a custom `DataTemplate`:

<snippet id='datagrid-loadondemandrowtemplate-xaml'/>

2. Set the template to the `LoadOnDemandRowTemplate` property of the DataGrid:

<snippet id='datagrid-setting-loadondemandrowtemplate-xaml'/>

The following image shows the row appearance after setting the `LoadOnDemandRowTemplate` property:

![Telerik UI for .NET MAUI DataGrid load on demand row with a customized Load More button template](../images/datagrid-rowtemplate.png)

>important For DataGrid LoadMore Template example, refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and go to the **DataGrid > LoadOnDemand** category.

## See Also

- [Load On Demand Overview]({%slug datagrid-features-loadondemand%})
- [Load On Demand Collection]({%slug datagrid-load-on-demand-collection%})
- [Load On Demand Event]({%slug datagrid-load-on-demand-event%})
- [Load On Demand Command]({%slug datagrid-load-on-demand-command%})
