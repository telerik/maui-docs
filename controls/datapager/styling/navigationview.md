---
title: Navigation View Styling
page_title: .NET MAUI DataPager Documentation - NavigationView Styling
description: Learn what are the styling options for the Telerik UI for .NET MAUI DataPager NavigationView view.
position: 2
slug: datapager-styling-navigationview
---

# Styling the .NET MAUI DataPager Navigation View

The DataPager for .NET MAUI provides a styling mechanism for customizing the look of the navigation view that presents the number of pages and the combo that allows you to select different page, by setting the `NavigationViewStyle` (`Style` with target type of `telerik:DataPagerNavigationView`) property.

The `NavigationViewStyle` uses as a target type the `telerik:DataPagerNavigationView`. The `DataPagerNavigationView` exposes the following properties:

* `DataPager` (`RadDataPager`)&mdash;Specifies the associated `Telerik.Maui.Controls.RadDataPager`.
* `LabelStyle` (`Style` with target type `Label`)&mdash;Specifies the style which applies to the label.
* `ComboBoxStyle` (`Style` with target type `RadComboBox`)&mdash;Specifies the associated `Telerik.Maui.Controls.RadDataPager`.
* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the page sizes view.

Here is an example.

Define the DataPager in XAML:

```XAML
<telerik:RadDataPager NavigationViewStyle="{StaticResource NavigationViewStyle}">
```

Set the styles to the page's resources:

```XAML
<Style x:Key="ComboStyle" TargetType="telerik:RadComboBox">

</Style>
<Style x:Key="LabelStyle" TargetType="Label">

</Style>
<Style x:Key="NavigationViewStyle" TargetType="telerik:DataPagerNavigationView">
    <Setter Property="ComboBoxStyle" Value="{StaticResource ComboStyle}" />
    <Setter Property="LabelsStyle" Value="{StaticResource LabelStyle}" />
</Style>
```

## Styling the Navigation ComboBox View

The DataPager for .NET MAUI provides a styling mechanism for customizing the look of the view that allows you to navigate to the pages by using the `NavigationComboBoxStyle` (`Style` with target type of `telerik:RadComboBox`) property.

The `NavigationComboBoxStyle` uses as a target type the `RadComboBox` control. Use the styling properties described in the [ComboBox Styling]({%slug combobox-styling%}) article to style the combobox part of the DataPager control. 

Here is an example:

```XAML
<telerik:RadDataPager NavigationComboBoxStyle="{StaticResource NavigationComboStyle}">
```

```XAML
<Style x:Key="NavigationComboStyle" TargetType="telerik:RadComboBox">
    <Setter Property="BorderColor" Value="#00897B" />
    <Setter Property="BorderThickness" Value="2" />
</Style>
```

## See Also

- [Paged Source]({%slug datapager-data-binding%})
- [Display Modes]({%slug datapager-display-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Integration with DataGrid]({%slug datapager-datagrid%})