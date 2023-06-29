---
title: Transitions
page_title: .NET MAUI SideDrawer Documentation - Transitions
description: Lear what are the different animation effects you can apply to the .NET MAUI SideDrawer when opening, closing.
position: 3
slug: sidedrawer-features-transitions
---

# .NET MAUI SideDrawer Transitions

Transitions are the animation effects applied to the side drawer while being opened and closed. The following properties are related to the SideDrawer transition:

* `DrawerTransitionDuration`(`double`)&mdash;Defines the duration of the chosen transition.
* `DrawerTransitionType`(enum of type `Telerik.Maui.Controls.SideDrawerTransitionType`)&mdash;Defines the transition of the component. This property can be set to one of the following values: 
	* `Fade`, `Push`, `Reveal`, `ReverseSlideOut`, `ScaleUp`, `SlideAling`, `SlideInOnTop`, `Custom`
	
* `DrawerTransitionFadeOpacity`(`double`)&mdash;Defines the opacity of the fade layer of the component. This controls the fade layer opacity on Android or the dim opacity on iOS.

## Built-in Transitions

The SideDrawer exposes predefined transitions. Set the transition type by using the `DrawerTransitionType` property of the SideDrawer. 

`DrawerTransitionType` is enumeration and exposes the following members:

* `Push` (the default one)
* `Fade`
* `Reveal`
* `ReverseSlideOut`
* `ScaleUp`
* `SlideAlong`
* `SlideInOnTop`
* `Custom`

Here is a sample snippet on how you can set `DrawerTransitionType` property of `RadSideDrawer`:

 <snippet id='sidedrawer-transition-xaml' />

Use the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
 ```

>tip In addition to the transition type, you can also control the transition duration and opacity value through `DrawerTransitionDuration` and `DrawerTransitionFadeOpacity` properties, respectively. For more details on this go to [Configuration]({%slug sidedrawer-features-configuration%}) topic.

### Examples

Check below some of the predefined transitions of `RadSideDrawer`.

* Default Push transition:

	![SideDrawer Push transition](images/sidedrawer_push.gif)

* SlideInOnTop transition - the drawer goes over the main content:

	![SideDrawer SlideInOnTop transition](images/sidedrawer_slidein.gif)

* ReverseSlideOut transition:

	![SideDrawer ReverseSlideOut](images/sidedrawer_reverseslideout.gif)

> For a runnable example with the SideDrawer Transitions scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **SideDrawer > Features**.

## See Also

- [Events]({%slug sidedrawer-features-events%})
- [Configuration]({%slug sidedrawer-features-configuration%})
- [Commands]({%slug sidedrawer-features-commands%})