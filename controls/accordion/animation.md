---
title: Animation
page_title: .NET MAUI Accordion Documentation - Animation
description: Check our &quot;Animation&quot; documentation article for Telerik .NET MAUI Accordion control.
position: 5
slug: accordion-animation
---

# .NET MAUI Accordion Animation

Telerik .NET MAUI Accordion provides an option to set the animation when expanding/collapsing an accordion item.

## Animation while expanding/collapsing

To enable or disable the animation you need to use the `IsAnimationEnabled` property of `RadAccordion`. By default, the Animation is enabled.

You could also customize the duration and easing through `AnimationDuration` and `AnimationEasing` properties.

* `AnimationDuration`(`int`)&mdash;Defines the duration of the animation while expanding/collapsing the AccordionItem. The default value is 500.
* `AnimationEasing`(`Microsoft.Maui.Easing`)&mdash;Specifies animation acceleration over time. The default value is Easing.Linear.

## Example

The snippet below shows how the `AnimationDuration`, `AnimationEasing` properties can be applied:

<snippet id='accordion-key-features-xaml'/>

The image below shows the result after running the snippet:

![.NET MAUI Accordion Animation](images/accordion_animation_1.png)

And the `RadAccordion` when all items are collapsed:

![.NET MAUI Accordion Animation](images/accordion_animation_2.png)

>important For the Accordion Animation example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [AccordionItem]({%slug accordion-accordion-item%})
- [Expand and Collapse states]({%slug accordion-expand-collapse-states%})
- [Item spacing]({%slug accordion-item-spacing%})
