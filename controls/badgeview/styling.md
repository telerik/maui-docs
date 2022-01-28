---
title: Badge Styling
page_title: .NET MAUI BadgeView Documentation | Badge Styling
description: "Check our &quot;Badge Styling&quot; documentation article for Telerik BadgeView for .NET MAUI."
position: 9
slug: badgeview-styling
---

# Badge Styling

Use the following properties to style the look of the badge:

* `BadgeText`(`string`)&mdash;Defines the badge text.
* `BadgeTextColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Defines the badge text color.
* `BadgeTextMargin`(`Microsoft.Maui.Thickness`)&mdash;Defines the mergin of the badge text.
* `BadgeFontSize`(`double`)&mdash; Defines the font size of the badge text.
* `BadgeFontFamily`(`string`)&mdash; Defines the badge text font family.
* `BadgeFontAttributes`(`Microsoft.Maui.Controls.FontAttributes`)&mdash; Defines the badge text font attributes.
* `BadgeBackgroundColor`(`Microsoft.Maui.Graphics.Color`)&mdash; Defines the background color of the badge.
* `BadgeBorderColor`(`Microsoft.Maui.Graphics.Color`)&mdash; Defines the badge border color. 
* `BadgeBorderThickness`(`Microsoft.Maui.Thickness`)&mdash; Defines the thickness of the badge border.
* `BadgeCornerRadius`(`Microsoft.Maui.Thickness`)&mdash; Defines the corner radius of the badge border.
* `BadgeMinimumWidth`(`double`)&mdash; Defines the minimum width of tha badge.
* `BadgeMinimumHeight`(`double`)&mdash; Defines the minimum height of the badge.

>important Use `BadgeType` for predefined types for the badge. If you set the `BadgeText` it will override the predefined icon for the badge type.

## Example

The BadgeView definition with some of the above properties set.

<snippet id='badgeview-styling'/>

Use the following namespace:

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
```

The final result:

![Badge Styling](images/badgeview-badge-styling.png)

>tip Badge Styling Example can be found inside the FeaturesCategory folder in  [SDKBrowser Demo Application]({%slug maui-demo-app%}).

## See Also

- [Configuration]({%slug badgeview-configuration%})
- [Badge Position and Alignment]({%slug badgeview-position-alignment%})
- [Badge Animation]({%slug badgeview-animation%})
- [CustomizAation]({%slug badgeview-customization%})