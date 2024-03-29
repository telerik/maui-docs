---
title: Header Settings
page_title: .NET MAUI Scheduler Header Documentation - Header Settings
description: Learn more about the Header settings of the Telerik UI for .NET MAUI Scheduler control.
position: 2
slug: header-settings
---

# Header Settings 

Customize the Scheduler header through the following configuration properties:

## Today Button

The Scheduler header includes an optional **Today** button, which navigates the currently active view to today's date. You can define whether the **Today** button will be available to the end users through the `IsTodayButtonVisible` boolean property. By default the **Today** button is enabled.

## Views Title and Format

Each view added to the Scheduler `ViewDefinitions` collection is listed inside the header. You can modify the representation of the views in the header through the `Title` and `HeaderTextFormat` properties of the view.

* `Title`&mdash;Specifies the title of the view definition.
* `HeaderTextFormat`&mdash;Defines the format string for the header text.

## Example

<snippet id='scheduler-header-properties' />

Check the result below:

![Telerik .NET MAUI Scheduler Header](../images/scheduler-header.png)

## See Also

- [Header Visual Structure]({% slug scheduler-header-visual-structure %})
- [Views]({% slug scheduler-views-overview %})