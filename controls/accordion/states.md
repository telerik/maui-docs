---
title: Expand&Collapse States
page_title: .NET MAUI Accordion Documentation - Expand&Collapse States
description: Check our &quot;Expand and Collapse States&quot; documentation article for Telerik .NET MAUI Accordion control.
position: 4
slug: accordion-expand-collapse-states
---

# .NET MAUI Accordion Expand and Collapse States

The purpose of this help article is to show you the expanded/collapsed states of the Telerik .NET MAUI Accordion control. 

## Collapsed/expanded States

In the Accordion control each item provides a header that expands when clicked, showing more information. The control is designed in such a way that opening one AccordionItem automatically closes the previously displayed content. 

There can be only one expanded item at a time indicated by `IsExpanded` property of the [AccordionItem]({%slug accordion-accordion-item%}) object.

## Collapse All Items

Through `CanCollapseAllItems` boolean property you can allow users to fully collapse the Accordion items. If `CanCollapseAllItems` is enabled, clicking on the header of an expanded Accordion item will collapse it.

## Example

The snippet below shows how the `CanCollapseAllItems` property can be applied:

<snippet id='accordion-key-features-xaml'/>

The image below shows the result after running the snippet:

![.NET MAUI Accordion States](images/accordion_keyfeatures_1.png)

And the `RadAccordion` when all items are collapsed:

![.NET MAUI Accordion States](images/accordion_keyfeatures_2.png)

>important A sample expand and collapse states example can be found in the Accordion/Features folder of the [SDK Samples Browser application]({%slug developer-focused-examples%}#sdk-browser-application).

## See Also

- [AccordionItem]({%slug accordion-accordion-item%})
- [Item spacing]({%slug accordion-item-spacing%})
- [Animation]({%slug accordion-animation%})