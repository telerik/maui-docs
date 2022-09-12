---
title: ExpanderHeader control
page_title: .NET MAUI Expander Documentation - Header control
description: "Check our ExpanderHeader control documentation article for Telerik Expander for .NET MAUI control."
position: 3
slug: expander-header
---

# .NET MAUI ExpanderHeader control

`ExpanderHeader` represents the Header of the Expander control which is used to show or hide the expandable container. ExpanderHeader provides a customizable Indicator to mark the current state of the Expander as well as BorderColor and BorderThickness properties to style the Header per your needs.

## Indicator Options

The indicator is the little triangle that is rotated according to whether the Expander control is expanded or collapsed. ExpanderHeader provides various options for customizing the look of the indicator via the following properties:

* `IndicatorText`&mdash;The indicator is represented by a string symbol that could be changed through IndicatorText property;
* `IndicatorFontFamily`&mdash;Specifies the indicator text FontFamily;
* `IndicatorFontSize`&mdash;Defines the indicator text font size;
* `IndicatorColor`&mdash;This property sets the color of the indicator;
* `IndicatorLocation`&mdash;This property is of type *ExpandCollapseIndicatorLocation* and is used to place the indicator to the left or to the right inside the Header;
* `IndicatorAnimationDuration`&mdash;Specifies the duration of the rotation animation of the indicator;
* `IndicatorAnimationEasing`&mdash;Specifies the easing of the rotation animation of the indicator;
* `IndicatorMargin`&mdash;This property is of type *Thickness* and sets the margin applied to the indicator;

## Border styling

You could apply `BorderColor` and `BorderThickness` properties of HeaderExpander to make it consistent with the design of your app. 

## Text styling

You could apply the `HeaderTextStyle`(Style with target type `Label`) property of HeaderExpander to change the Text Style of the Header.

## Example

Check the example below on how the Indicator options and border properties could be applied:

<snippet id='expander-features-expanderheader'/>

## See Also

- [Configuration]({% slug expander-configuration%})
