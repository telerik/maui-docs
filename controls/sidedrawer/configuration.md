---
title: Configuration
page_title: .NET MAUI SideDrawer Documentation - Configuration
description: Lear what are the options to configure the .NET MAUI SideDrawer and how to change the drawer position and interactivity.
position: 2
slug: sidedrawer-features-configuration
---

# Configure the .NET MAUI SideDrawer

This article explains all configuration options that the SideDrawer control provides.

## Content

Use the folloing properties to define content of the SideDrawer control:

* `DrawerContent`(`View`)&mdash;Specifies the drawer (initially hidden) content.
* `MainContent`(`View`)&mdash;Specifies the (initially visible) content of the component.

## Drawer Behavior

* `IsOpen`(`bool`)&mdash;Specifies a value indicating if the drawer content is visible.
* `DrawerLength`(`double`)&mdash;Defines how much the drawer content is extended over the main content in opened position.
* `DrawerLocation`(`SideDrawerLocation`)&mdash;Specifies the location from which the drawer will be opened. The following options are available:
	* `Left` 
	* `Right`
	* `Top`
	* `Bottom`

* `AreGesturesEnabled`(`bool`)&mdash;This is a mobile exclusive property which specifies ability for gestures to open and close the drawer.
* `TouchTargetThreshold`(`double`)&mdash;Defines the touchable area (number of pixels from the screen edges) that will allow to open the `DrawerContent`. 

## Keep Drawer Open and Main Content Area Active

By default the SideDrawer drawer content closes when user clicks/taps outside of it. By setting the `TapOutsideToClose`(`bool`) to `false`, the drawer content remains open if the user taps/clicks outside of it and the main content area remains active. The default value of `TapOutsideToClose` is `true`.

![.NET MAUI SideDrawer Main Content Area active Started](images/sidedrawer-main-content-active.gif)

> For a runnable example with the SideDrawer Location scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **SideDrawer > Features**.

## See Also

- [Commands]({%slug sidedrawer-features-commands%})
- [Transitions]({%slug sidedrawer-features-transitions%})
- [Events]({%slug sidedrawer-features-events%})
