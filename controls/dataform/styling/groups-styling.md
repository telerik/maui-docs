---
title: Group Styling
page_title: .NET MAUI DataForm Documentation | Group Styling
description: "Review the available Styling options which DataForm for .NET MAUI control provides when groups are applied."
position: 2
slug: dataform-group-styling
---

# .NET MAUI DataForm Group Styling

The DataForm control for .NET MAUI provides styling options for customizing the apperance of its group headers. You can apply a style to the whole header, or only to the header label.

The `DataFormGroup` class exposes the following `Style` properties:

* `HeaderStyle`(of type `Style` with target type `DataFormGroupHeaderView`)&mdash;Defines the header view style.
* `HeaderLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the header label style.

##HeaderStyle

To style the `DataFormGroupHeaderView` use the following properties:

* `BackgroundColor`&mdash;Defines the background color of the header.
* `BorderColor`&mdash;Defines the border color of the header.
* `BorderThickness`&mdash;Specifies the border thickness of the header.
* `HeaderLabelStyle` (of type `Style` with target type `Label`)&mdash;Defines the header label style.

##Example

The following examples demonstrate how to use the styling properties of the DataFormGroup.

**Define the `RadDataForm` and the groups**

<snippet id='dataform-group-styling' />

**Define the `HeaderStyle`**

<snippet id='dataform-group-styling-header-view-style' />

**Define the `HeaderLabelStyle` of the first DataForm group**

<snippet id='dataform-group-styling-header-label-style' />

**Define the `HeaderLabelStyle` of the second DataForm group**

<snippet id='dataform-group-styling-header-label-style-alt' />

Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

The following image shows what the DataForm control looks like when the styles described above are applied:

![.NET MAUI DataForm Group Styling](../images/dataform-group-styling.png)