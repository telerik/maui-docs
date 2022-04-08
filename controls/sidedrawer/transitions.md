---
title: Transitions
page_title: .NET MAUI SideDrawer Documentation | Transitions
description: Check our &quot;Transitions&quot; documentation article for Telerik UI for .NET MAUI SideDrawer control.
position: 3
slug: sidedrawer-features-transitions
---

# Transitions

Transitions are the animation effects applied to the side drawer while it is being opened and closed. The following properties are related to the sideDrawer transition:

* `DrawerTransitionDuration`(`double`)&mdash;Defines the duration of the chosen transition.
* `DrawerTransitionType`(enum of type `Telerik.Maui.Controls.SideDrawerTransitionType`)&mdash;Defines the transition of the component. This property can be set to one of the following values: 
	* `Fade`, `Push`, `Reveal`, `ReverseSlideOut`, `ScaleUp`, `SlideAling`, `SlideInOnTop`, `Custom`
	
* `DrawerTransitionFadeOpacity`(`double`)&mdash;Defines the opacity of the fade layer of the component. This controls the fade layer opacity on Android or the dim opacity on iOS.

## Built-in Transitions

The SideDrawer exposes several predefined transitions. Set the transition type by using the `DrawerTransitionType` property of the SideDrawer. 

DrawerTransitionType is enumeration and exposes the following members:

* `Push` (the default one)
* `Fade`
* `Reveal`
* `ReverseSlideOut`
* `ScaleUp`
* `SlideAlong`
* `SlideInOnTop`
* `Custom`

Here is a sample snippet on how you can set `DrawerTransitionType` property of RadSideDrawer:

 <snippet id='sidedrawer-transition-xaml' />

Add the following namespace:

 ```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
 ```

>tip In addition to the transition type, you can also control the transition duration and opacity value through `DrawerTransitionDuration` and `DrawerTransitionFadeOpacity` properties, respectively. For more details on this go to [Configuration]({%slug sidedrawer-features-properties%}) topic.

### Examples

Check below some of the predefined transitions of RadSideDrawer.

* Default Push transition:

	![SideDrawer Push transition](images/sidedrawer_push.gif)

* SlideInOnTop transition - the drawer goes over the main content:

	![SideDrawer SlideInOnTop transition](images/sidedrawer_slidein.gif)

* ReverseSlideOut transition:

	![SideDrawer ReverseSlideOut](images/sidedrawer_reverseslideout.gif)

>important A sample Transitions examples can be found in the SideDrawer/Features folder of the [SDK Browser MAUI application]({%slug maui-demo-app%}).

## See Also

- [Getting-Started]({%slug sidedrawer-getting-started%})
- [Events]({%slug sidedrawer-features-events%})
- [Configuration]({%slug sidedrawer-features-configuration%})
- [Commands]({%slug sidedrawer-features-commands%})