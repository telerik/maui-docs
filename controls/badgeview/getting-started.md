---
title: Getting Started
page_title: .NET MAUI BadgeView Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI BadgeView control and add the control to your .NET MAUI project."
position: 2
slug: badgeview-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI BadgeView by adding the control to your project.

At the end, you will be able to achieve the following result.

![Getting Started Example](images/badgeview-getting-started.png)

## Prerequisites

Before adding the BadgeView, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When the your .NET MAUI application is set up, you are ready to add a BadgeView control to your page.

 ```XAML
<telerikPrimitives:RadBadgeView/>
 ```
 ```C#
var badge = new RadBadgeView();
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
 ````

1. Set `Content` and `BadgeText` properties. Note that the Badge marker (indicator), which is part of the BadgeView, will be visualized only if the `Content` property of the BadgeView is set.

 <snippet id='badgeview-getting-started-xaml'/>
 <snippet id='badgeview-getting-started-csharp'/>

>important For examples on getting started, refer to the [SDKBrowser Demo Application]({%slug maui-demo-app%}).

## See Also

- [Configuration]({%slug badgeview-configuration%})
- [Badge Position and Alignment]({%slug badgeview-position-alignment%})
- [Badge Animation]({%slug badgeview-animation%})
- [Badge Types]({%slug badgeview-predefined-badges%})
