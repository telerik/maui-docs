---
title: Badge Types
page_title: .NET MAUI BadgeView Documentation | Predefined Badges
description: "Check our &quot;Predefined Badges&quot; documentation article for Telerik BadgeView for .NET MAUI."
tags: badge, marker, indicator, badgeview for .net maui, badge for .net maui
position: 5
tags: badge types, badge for .net maui, badgeview
slug: badgeview-predefined-badges
---

# Badge Types

![Badge Types](images/badgeview-badge-types.png)

You can change the Badge type using one of the predefined badge types. 

* `BadgeType`(of type *Telerik.XamarinForms.Primitives.BadgeType*): Specifies the type of the Badge. The default value is `Default`

The available options are:  

* Default 
* Available 
* Away 
* DoNotDisturb 
* Offline 
* OutOfOffice
* Dot  
* Add 
* Remove 
* Rejected 

## Example

Define the BadgeView:

<snippet id='badgeview-badge-types'/>

Use the following namespace:

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility" 
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility" 
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"                        
```

The result:

![Badge Types](images/badgeview-badge-types-example.png)

Badge Types example can be found in [SDKBrowser Demo Application]({%slug maui-demo-app%}), just navigate to BadgeView -> Features category.


## See Also

- [Key Features]({%slug badgeview-key-features%})
- [Badge Position, Alignment and Offset]({%slug badgeview-position-alignment%})
- [Badge Animation]({%slug badgeview-animation%})
- [Styling]({%slug badgeview-styling%})
- [Customizaation]({%slug badgeview-customization%})
