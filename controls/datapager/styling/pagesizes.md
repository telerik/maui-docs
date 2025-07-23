---
title: Page Sizes Styling
page_title: .NET MAUI DataPager Documentation - Page Sizes Styling
description: Learn what are the styling options for the Telerik UI for .NET MAUI DataPager PageSizes view.
position: 3
slug: datapager-styling-pagesize
---

# Styling the .NET MAUI DataPager PageSizes View

The DataPager for .NET MAUI provides a styling mechanism for customizing the look of the view that allows you to navigate to the page sizes by using the `PageSizesViewStyle` (`Style` with target type of `telerik:DataPagerPageSizesView`) property.

The `telerik:PageSizesViewStyle` uses as a target type the `telerik:DataPagerPageSizesView`. The `DataPagerPageSizesView` exposes the following properties:

* `DataPager` (`RadDataPager`)&mdash;Specifies the associated `Telerik.Maui.Controls.RadDataPager`.
* `LabelStyle` (`Style` with target type `Label`)&mdash;Specifies the style which applies to the label.
* `ComboBoxStyle` (`Style` with target type `RadComboBox`)&mdash;Specifies the associated `Telerik.Maui.Controls.RadDataPager`.
* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the page sizes view.

Here is an example demonstrating how to use `PageSizesViewStyle`.

**1.** Define the DataPager in XAML:

```XAML
<telerik:RadDataPager PageSizesViewStyle="{StaticResource PageSizesViewStyle}"
```

**2.** Set the styles to the page's resources:

```XAML
<Style x:Key="ComboStyle" TargetType="telerik:RadComboBox">

</Style>
<Style x:Key="LabelStyle" TargetType="Label">

</Style>
<Style x:Key="PageSizesViewStyle" TargetType="telerik:DataPagerPageSizesView">
    <Setter Property="ComboBoxStyle" Value="{StaticResource ComboStyle}" />
    <Setter Property="LabelStyle" Value="{StaticResource LabelStyle}" />
</Style>
```

## See Also

- [Paged Source]({%slug datapager-data-binding%})
- [Display Modes]({%slug datapager-display-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Integration with DataGrid]({%slug datapager-datagrid%})