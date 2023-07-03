---
title: Badge Types
page_title: .NET MAUI BadgeView Documentation - Predefined Badges
description: Check our &quot;Predefined Badges&quot; documentation article for Telerik UI for .NET MAUI BadgeView
tags: badge, marker, indicator, badgeview for .net maui, badge for .net maui
position: 5
tags: badge types, badge for .net maui, badgeview
slug: badgeview-predefined-badges
---

# Badge Types

The `BadgeView` supports a set of Badge indicator types.  

![Badge Types](images/badgeview-badge-types.png)

To change and specify the Badge type, use the `BadgeType`(of type `Telerik.Maui.Controls.Compatibility.Primitives.BadgeType`) property, which exposes the following options:

* (Default) `Default`
* `Available`
* `Away`
* `DoNotDisturb`
* `Offline`
* `OutOfOffice`
* `Dot`
* `Add`
* `Remove`
* `Rejected`

The following example demonstrates how to set the type of the Badge indicator.

1. Define the BadgeView:

 <snippet id='badgeview-badge-types'/>

1. Use the `telerik` namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"                    
 ```

The following image shows the final result.

![Badge Types](images/badgeview-badge-types-example.png)

> For the Badge Types example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to BadgeView -> Features category.


## See Also

- [Configuration]({%slug badgeview-configuration%})
- [Badge Position, Alignment and Offset]({%slug badgeview-position-alignment%})
- [Badge Animation]({%slug badgeview-animation%})
- [Styling]({%slug badgeview-styling%})
- [Customization]({%slug badgeview-customization%})
