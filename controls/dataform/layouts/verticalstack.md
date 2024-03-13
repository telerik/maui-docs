---
title: VerticalStackLayout
page_title: .NET MAUI DataForm Documentation - VerticalStackLayout
description: Review the Telerik UI for .NET MAUI DataForm VerticalStackLayout option.
position: 1
slug: dataform-layouts-verticalstack
---

# .NET MAUI DataForm VerticalStackLayout Definition

The `DataFormVerticalStackLayout` definition allows you to arrange the items in a vertical stack layout.

Use the `Spacing`(`double`) property to specify the spacing in pixels between the items in the layout. Default value is `24`.

![.NET MAUI DataForm Stack Layout Definition](../images/dataform-verticalstack-layout-desktop.png)

`RadDataForm` XAML definition with `DataFormVerticalStackLayout` applied:

<snippet id='dataform-layouts-stack'/>

The `ViewModel` used for the DataForm editors:

<snippet id='dataform-editors-model'/>

where the `local` points to the namespace where the `EditorsViewModel` is defined.

> For a runnable example with the DataForm VerticalStackLayout scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataForm > Layouts** category.

## See Also

- [Grid Layout]({%slug dataform-layouts-grid%})
- [Custom Layout]({%slug dataform-layouts-custom%})