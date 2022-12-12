---
title: AccordionItem control
page_title: .NET MAUI Accordion Documentation - AccordionItem control
description: Check our &quot;AccordionItem control&quot; documentation article for Telerik .NET MAUI Accordion control.
position: 2
slug: accordion-accordion-item
---

# AccordionItem control

This articles explains the configuration options of the AccordionItem.

## AccordionItem Header

You could either apply `HeaderText` property or use the `AccordionItemHeader` content control which provides a set of useful properties for customizing the look & feel of the Header.

The indicator is the little triangle that is rotated according to whether the AccordionItem control is expanded or collapsed. AccordionItemHeader provides various options for customizing the look of the indicator via the following properties:

* `IndicatorText`&mdash;The indicator is represented by a string symbol that could be changed through IndicatorText property;
* `IndicatorFontFamily`&mdash;Specifies the indicator text FontFamily;
* `IndicatorFontSize`&mdash;Defines the indicator text font size;
* `IndicatorColor`&mdash;Specifies sets the color of the indicator;
* `IndicatorLocation`(`ExpandCollapseIndicatorLocation`)&mdash;Positions the indicator to the left or to the right inside the Header;
* `IndicatorAnimationDuration`&mdash;Specifies the duration of the rotation animation of the indicator;
* `IndicatorAnimationEasing`&mdash;Specifies the easing of the rotation animation of the indicator;
* `IndicatorMargin`(`Thickness`)&mdash;Specifies the margin applied to the indicator;

## IsExpanded
	
IsExpanded is a Boolean property to indicate the currently expanded state of the AccordionItem.	
	
## Border Styles

You could utilize `BorderColor`, `BorderThickness` and `CornerRadius` properties of RadAccordionItem to change the way the Border around the control looks.

The following snippet shows how to customize the `AccordionItemHeader`:

<snippet id='accordion-features-accordionitem' />

Next image displays how the `RadAccordion` will look with thus defined items:

![.NET MAUI AccordionItem](images/accordion_accordionitem.png)

>important A sample AccordionItem example can be found in the Accordion/Features folder of the [SDK Samples Browser application]({%slug developer-focused-examples%}).

## See Also

- [Expand and Collapse states]({%slug accordion-expand-collapse-states%})
- [Item spacing]({%slug accordion-item-spacing%})
- [Animation]({%slug accordion-animation%})
