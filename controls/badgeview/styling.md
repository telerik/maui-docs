---
title: Styling
page_title: .NET MAUI BadgeView Documentation - Styling
description: "Check our &quot;Badge Styling&quot; documentation article for Telerik BadgeView for .NET MAUI."
position: 8
slug: badgeview-styling
---

# Styling

The BadgeView exposes a number of properties which allow you to style the appearance of the Badge indicator.

To style the Badge, use the following options:

* `BadgeText`(`string`)&mdash;Defines the Badge text.
* `BadgeTextColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Defines the Badge text color.
* `BadgeTextMargin`(`Microsoft.Maui.Thickness`)&mdash;Defines the margin of the Badge text.
* `BadgeFontSize`(`double`)&mdash;Defines the font size of the Badge text.
* `BadgeFontFamily`(`string`)&mdash;Defines the font family of the Badge text.
* `BadgeFontAttributes`(`Microsoft.Maui.Controls.FontAttributes`)&mdash;Defines the font attributes of the Badge text.
* `BadgeBackgroundColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Defines the background color of the Badge.
* `BadgeBorderColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Defines the Badge border color.
* `BadgeBorderThickness`(`Microsoft.Maui.Thickness`)&mdash;Defines the thickness of the Badge border.
* `BadgeCornerRadius`(`Microsoft.Maui.Thickness`)&mdash;Defines the corner radius of the Badge border.
* `BadgeMinimumWidth`(`double`)&mdash;Defines the minimum width of the Badge.
* `BadgeMinimumHeight`(`double`)&mdash;Defines the minimum height of the Badge.

>important To configure the predefined types of the Badge, use the `BadgeType` property. Setting the `BadgeText` will override the predefined icon for the Badge type.

The following example demonstrates how to style the Badge indicator.

1. Define the BadgeView with some of the above properties.

 <snippet id='badgeview-styling'/>

1. Add the `telerik` namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

The following image shows the final result.

![Badge Styling](images/badgeview-badge-styling.png)

> For the BadgeView Styling example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to BadgeView -> Features category.

## See Also

- [Configuration]({%slug badgeview-configuration%})
- [Badge Position and Alignment]({%slug badgeview-position-alignment%})
- [Badge Animation]({%slug badgeview-animation%})
- [Customization]({%slug badgeview-customization%})
