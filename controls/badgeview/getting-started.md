---
title: Getting Started
page_title: .NET MAUI BadgeView Documentation - Getting Started
description: "Get started with the Telerik UI for .NET MAUI BadgeView control and add the control to your .NET MAUI project."
position: 2
slug: badgeview-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI BadgeView by adding the control to your project.

At the end, you will be able to achieve the following result.

![BadgeView Getting Started](images/badgeview-getting-started.png)

## Prerequisites

Before adding the BadgeView, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When the your .NET MAUI application is set up, you are ready to add a BadgeView control to your page.

 ```XAML
<telerik:RadBadgeView/>
 ```
 ```C#
var badge = new RadBadgeView();
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ````

1. Set `Content` and `BadgeText` properties. Note that the Badge marker (indicator), which is part of the BadgeView, will be visualized only if the `Content` property of the BadgeView is set.

 <snippet id='badgeview-getting-started-xaml'/>
 <snippet id='badgeview-getting-started-csharp'/>

> For the BadgeView Getting Started example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Additional Resources

- [.NET MAUI BadgeView product page](https://www.telerik.com/maui-ui/badgeview)
- [.NET MAUI BadgeView forum page](https://www.telerik.com/forums/maui?tagId=1900)
- [Telerik .NET MAUI blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)


## See Also

- [Configuration]({%slug badgeview-configuration%})
- [Badge Position and Alignment]({%slug badgeview-position-alignment%})
- [Badge Animation]({%slug badgeview-animation%})
- [Badge Types]({%slug badgeview-predefined-badges%})
