---
title: Special Slots Styling
page_title: .NET MAUI Scheduler Documentation - Special Slots Styling
description: Learn how to style the special slots in the Telerik .NET MAUI Scheduler control.
position: 7
slug: scheduler-special-slots-styling
---

# .NET MAUI Scheduler Special Slots Styling

The Scheduler for .NET MAUI control makes it easy to customize the look & feel of the special slots.

Scheduler exposes an `SpecialSlotStyleSelector` (type `Telerik.Maui.Controls.IStyleSelector`) property which conditionally applies different styles to special slots depending on some logic.

In the example special slots are used to distinguish the non-working hours. In addition, the custom `SpecialSlotStyleSelector` applies separate style non-working hours during the week day and the weekend.

**1.** Create a custom Style Selector class:

<snippet id='scheduler-specialslots-styleselector' />

**2.** Add the style selector with the corresponding styles to the page resources:

<snippet id='scheduler-specialslots-style' />

**3.** Add the ViewModel class with the `SpecialSlotsSource` defined:

<snippet id='scheduler-specialslots-viewmodel' />

**4.** Define the Scheduler with the `SpecialSlotStyleSelector` property applied to the view definitions:

<snippet id='scheduler-specialslotsstyling-definition' />

Check the result on Windows below:

![Scheduler Special Slots Styling](images/scheduler-specialslots-styling.png)

## See Also

- [Special Slots]({%slug scheduler-special-slots%})
- [SpecialSlot Template]({%slug scheduler-special-slot-template%})