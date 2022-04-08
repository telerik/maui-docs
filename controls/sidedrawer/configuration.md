---
title: Configuration
page_title: .NET MAUI SideDrawer Documentation | Configuration
description: Check our &quot;configuration&quot; documentation article for Telerik UI for .NET MAUI SideDrawer control.
position: 2
slug: sidedrawer-features-configuration
---

# Configuration

This article explains all configuration options that the SideDrawer control provides.

* `DrawerContent`(`View`)&mdash;Specifies the drawer (initially hidden) content.
* `MainContent`(`View`)&mdash;Specifies the (initially visible) content of the component.
* `IsOpen`(`bool`)&mdash;Specifies a value indicating if the drawer content is visible.
* `DrawerLength`(`double`)&mdash;Defines how much the drawer content should be extended over the main content in opened position.
* `DrawerLocation`(`SideDrawerLocation`)&mdash;Specifies the location from which the drawer will be opened. The following options are available:
	* `Left` 
	* `Right`
	* `Top`
	* `Bottom`

* `AreGesturesEnabled`(`bool`)&mdash;Specifies ability for gestures to open and close the drawer.
* `TouchTargetThreshold`(`double`)&mdash;Defines the touchable area (number of pixels from the screen edges) that will allow to open the DrawerContent. 

>important A sample Location example can be found in the SideDrawer/Features folder of the [SDK Samples Browser application]({%slug developer-focused-examples%}).

## See Also

- [Getting-Started]({%slug sidedrawer-getting-started%})
- [Commands]({%slug sidedrawer-features-commands%})
- [Transitions]({%slug sidedrawer-features-transitions%})
- [Events]({%slug sidedrawer-features-events%})
