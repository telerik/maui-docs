---
title: Navigation View Styling
page_title: .NET MAUI DataPager Documentation - NavigationView Styling
description: Learn what are the styling options for the Telerik UI for .NET MAUI DataPager NavigationView view.
position: 2
slug: datapager-styling-navigationview
---

# Styling the .NET MAUI DataPager Navigation View

The DataPager for .NET MAUI provides a styling mechanism for customizing the look of the navigation view, which presents the number of pages and the combo box for selecting different pages.

To style the Navigation View, utilize the `NavigationViewStyle` property (of type `Style` with a target type of `telerik:DataPagerNavigationView`). 

The `DataPagerNavigationView` exposes the following properties:
* `DataPager` (`RadDataPager`)&mdash;Specifies the associated `Telerik.Maui.Controls.RadDataPager`.
* `LabelStyle` (`Style` with target type `Label`)&mdash;Specifies the style which applies to the label.
* `ComboBoxStyle` (`Style` with target type `RadComboBox`)&mdash;Specifies the associated `Telerik.Maui.Controls.RadDataPager`.
* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the page sizes view.

Here is an example demonstrating how to use the `NavigationViewStyle` property.

**1.** Define the DataPager in XAML:

```XAML
<telerik:RadDataPager NavigationViewStyle="{StaticResource NavigationViewStyle}">
```

**2.** Set the styles to the page's resources:

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

To customize the appearance of the ComboBox view that allows the navigation to a specific page, use the `NavigationComboBoxStyle` (`Style` with target type of `telerik:RadComboBox`) property.

The target type of the `NavigationComboBoxStyle` is the `RadComboBox` control. Use the styling properties described in the [ComboBox Styling]({%slug combobox-styling%}) article to style the ComboBox part of the DataPager control. 

Here is an example demonstrating how to use the `NavigationComboBoxStyle` property.

**1.** Define the DataPager in XAML:

```XAML
<telerik:RadDataPager NavigationComboBoxStyle="{StaticResource NavigationComboStyle}">
```

**2.** Set the style for the `NavigationComboStyle` to the page's resources:

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