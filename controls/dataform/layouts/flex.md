---
title: FlexLayout
page_title: .NET MAUI DataForm Documentation | FlexLayout
description: Review the .NET MAUI DataForm &quot;FlexLayout&quot; option.
position: 3
slug: dataform-layouts-flex
---

# .NET MAUI DataForm FlexLayout Definition

The `DataFormFlexLayout` definition allows you to arrange the items in a flex layout. Use the followinfg properties for additinal customization:

* `AlignItems`(of type `Microsoft.Maui.Layouts.FlexAlignItems`)&mdash;Specifies how the layout engine distributes the space between and around children along the cross axis. Default value is `Stretch`.
* `AlignContent`(of type `Microsoft.Maui.Layouts.FlexAlignContent`)&mdash;Specifies how the layout engine distributes the space between and around children that are laid out on multiple lines. Default value is `Stretch`.
* `JustifyContent`(of type `Microsoft.Maui.Layouts.FlexJustify`)&mdash;Specifies how space is distributed between and around children along the main axis. Default value is `Start`.
* `Direction`(of type `Microsoft.Maui.Layouts.FlexDirection`)&mdash;Specifies the drection and main axis of the children (DataForm editors)Default value is `Row`.
* `Position`(of type `Microsoft.Maui.Layouts.FlexPosition`)&mdash;Determines whether the position of children are relative to each other, or by using fixed values.Default value is `Relative`.

> For more details about the FlexLayout review the official [FlexLayout Microsoft Documentation](https://docs.microsoft.com/en-us/dotnet/maui/user-interface/layouts/flexlayout).

![DataForm Flex Layout Definition](images/dataform-layouts-stack.png)

**RadDataForm XAML definition with StackLayout applied:**

<snippet id='dataform-layouts-flex'/>

**The Model used for the DataForm editors**

<snippet id='dataform-editors-model'/>
