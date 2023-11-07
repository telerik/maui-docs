---
title: Special Slot Template
page_title: .NET MAUI Scheduler Documentation - Special Slot Template
description: Learn more about the special slot template feature in the Telerik UI for .NET MAUI Scheduler control.
position: 1
slug: scheduler-special-slot-template
---

# SpecialSlot Template

By default the special slots are marked with a different background, so that they are easily noticable across the view. In addition you can show a content of your choice inside special slots through the `SpecialSlotTemplate` property of the view definitions.

* `SpecialSlotTemplate(DataTemplate)`&mdash;Defines the template of the special slots.

Here is a quick example how to apply a custom slot template to the Scheduler:

**1.** Add the template to the page resources:

<snippet id='scheduler-customslots-resources' />

**2.** Add the Scheduler definition with the `SpecialSlotTemplate` applied:

<snippet id='scheduler-special-slots-template' />

Check the image below which shows the applied `SpecialSlotTemplate`:

![Telerik .NET MAUI Scheduler Special Slot Template](../images/scheduler-specialslots-template.png)

## See Also

- [Special Slots]({%slug scheduler-special-slots%})
- [Views]({% slug scheduler-views-overview %})