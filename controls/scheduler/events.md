---
title: Events
page_title: .NET MAUI Scheduler Documentation - Events
description: Learn about the events that the Telerik UI for .NET MAUI Scheduler control exposes and find out how to use them to configure the UI component.
position: 15 
slug: scheduler-events
---

# .NET MAUI Scheduler Events

The Telerik UI for .NET MAUI Scheduler component exposes a set of events that users trigger through interaction. You can handle these events and execute custom logic based on user action.

Here is a list of the available events:

* `AppointmentTapped`&mdash;occurs when the user taps on an appointment. The `AppointmentTapped` event handler receives two parameters:
    * The sender argument, which is of type `object`, but can be cast to the `RadScheduler` type.
    * A `TappedEventArgs<Occurrence>` object which provides the appointment occurrence through its `Data` property.
* `AppointmentDoubleTapped`&mdash;occurs when the user double taps on an appointment. The `AppointmentDoubleTapped`event handler receives two parameters:
    * The sender argument, which is of type `object`, but can be cast to the `RadScheduler` type.
    * A `TappedEventArgs<Occurrence>` object which provides the appointment occurrence through its `Data` property.
* `SlotTapped`&mdash;occurs when the user taps on a slot. The `SlotTapped` event handler receives two parameters:
    * The sender argument, which is of type `object`, but can be cast to the `RadScheduler` type.
    * A `TappedEventArgs<Slot>` object which provides the slot through its `Data` property.
* `SlotDoubleTapped`&mdash;occurs when the user double taps on a slot. The `SlotDoubleTapped` event handler receives two parameters:
    * The sender argument, which is of type `object`, but can be cast to the `RadScheduler` type.
    * A `TappedEventArgs<Slot>` object which provides the slot through its `Data` property.
* `MonthDayTapped`&mdash;occurs when the user taps on a month day. The `MonthDayTapped` event handler receives two parameters:
    * The sender argument, which is of type `object`, but can be cast to the `RadScheduler` type.
    * A `TappedEventArgs<DateTime>` object which provides the month day through its `Data` property.
* `MonthDayDoubleTapped`&mdash;occurs when the user double taps on a month day. The `MonthDayDoubleTapped` event handler receives two parameters:
    * The sender argument, which is of type `object`, but can be cast to the `RadScheduler` type.
    * A `TappedEventArgs<DateTime>` object which provides the month day through its `Data` property.

* `AgendaItemTapped`&mdash;occurs when the user taps on an agenda item. This event only applies to `Agenda` view and is not raised in `Day`, `Week`, `Month`, or `Multiday` views. The `AgendaItemTapped` event handler receives two parameters:
    * The sender argument, which is of type `object`, but can be cast to the `RadScheduler` type.
    * A `TappedEventArgs<SchedulerNode>` object which provides the agenda item occurrence through its `Data` property. The `Data` property can be one of the following types:
        * `AgendaMonthNode`&mdash;Represents the model for month group headers in the agenda view.
        * `AgendaWeekNode`&mdash;Represents the model for week group headers in the agenda view.
        * `AgendaDayNode`&mdash;Represents the model for day group headers in the agenda view.
        * `AppointmentNode`&mdash;Represents the model of the views that are used to visualize appointments.

* `AgendaItemDoubleTapped`&mdash;occurs when the user taps on an agenda item. This event only applies to `Agenda` view and is not raised in `Day`, `Week`, `Month`, or `Multiday` views. The `AgendaItemTapped` event handler receives two parameters:
    * The sender argument, which is of type `object`, but can be cast to the `RadScheduler` type.
    * A `TappedEventArgs<SchedulerNode>` object which provides the agenda item occurrence through its `Data` property. The `Data` property can be one of the following types:
        * `AgendaMonthNode`&mdash;Represents the model for month group headers in the agenda view.
        * `AgendaWeekNode`&mdash;Represents the model for week group headers in the agenda view.
        * `AgendaDayNode`&mdash;Represents the model for day group headers in the agenda view.
        * `AppointmentNode`&mdash;Represents the model of the views that are used to visualize appointments.

## See Also

- [Views]({% slug scheduler-views-overview %})
- [Appointments]({% slug appointments-overview %})