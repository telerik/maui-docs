---
title: Configuration
page_title: .NET MAUI Expander Documentation - Configuration
description: "Check our Configuration documentation article for Telerik Expander for .NET MAUI control."
position: 2
slug: expander-configuration
---

# .NET MAUI Expander Configuration

The purpose of this help article is to show you how to configure the Telerik .NET MAUI Expander control. 

## Collapsed/expanded states

RadExpander provides an expandable container which can host any content. You can show or hide this content by interacting with the `Header` of the control. The default state of RadExpander is collapsed.

You could use `IsExpanded` boolean property to switch the current state of the control.

## Expander header

You could either apply `HeaderText` property or use the `ExpanderHeader` content control which provides a set of useful properties for customizing the way the header looks. For more details refer to [ExpanderHeader control]({% slug expander-header%}) topic.

<snippet id='expander-features-headerlocation'/>

## Animation while expanding or collapsing

To enable or disable the animation you need to use the `IsAnimationEnabled` property of RadExpander. By default, the Animation is enabled.

You could also customize the duration and easing (acceleration over time) through `AnimationDuration`(in ms) and `AnimationEasing` (of type *Xamarin.Forms.Easing*) properties.

## Border styling

You could apply `BorderColor` and `BorderThickness` properties of RadExpander to make it consistent with the design of your app.

>note ExpanderHeader also provides means for customizing its border, you can learn more about this in the [ExpanderHeader: Border Styling]({%slug expander-header%}#border-styling) article.

Check the example below on how the border settings could be defined:

<snippet id='expander-features-borderstyling'/>

## Text styling

To customize the text inside the header you have to use the `HeaderTextStyle` property. If `HeaderTextStyle` is not set, the text inside is bold by default.

The following code shows how to declare the HeaderTextStyle property in the Expander:

<snippet id='expander-features-headertext-styling'/>

## See Also

- [Getting Started]({% slug expander-getting-started%})
