---
title: Special Slots
page_title: .NET MAUI Scheduler Documentation - Special Slots
description: Learn more about the special slots feature in the Telerik UI for .NET MAUI Scheduler control.
position: 0
slug: scheduler-special-slots
---

# Special Slots

The Telerik UI for .NET MAUI Scheduler control exposes an option to define the special and read-only slots and apply different styles to them. You need to prepare a collection of Slot objects and assign it to `SpecialSlotsSource` property of the `RadScheduler` instance.

Every Slot has the following properties:

* `Start (type DateTime)`&mdash;Defines the start date of the slot.
* `End (type DateTime)`&mdash;Defines the end date of the slot.
* `ReccurencePattern`&mdash;Defines whether the slot will be displayed for repeating days.
* `IsReadOnly`&mdash;When set to `True` the slot is disabled.
* `TimeZone ( type TimeZoneInfo)`&mdash;Specifies the slot time zone. 

Below you can find a quick example how to create special slots.

First, create a ViewModel class with a collection of `Slot` objects. In the example two repeating slots are added for rest hours during weekdays. 

<snippet id='scheduler-specialslots-viewmodel' />

Then, add `RadScheduler` definition with some sample views with `SpecialSource` property applied:

<snippet id='scheduler-special-slots' />

Last step is to set the BindingContext to the ViewModel class:

<snippet id='scheduler-specialslots-setvm' /> 

# See Also

- [SpecialSlots Template]({%slug scheduler-special-slot-template%})
- [Views]({% slug scheduler-views-overview %})
