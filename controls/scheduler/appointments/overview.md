---
title: Appointments Overview
page_title: .NET MAUI Scheduler Documentation - Appointments Overview
description: Learn more about the appointments feature in Telerik UI for .NET MAUI Scheduler control.
position: 0
slug: appointments-overview
---

# Appointments 

Telerik UI for .NET MAUI Scheduler control provide functionality to display appointments by setting its `AppointmentsSource` property. `AppointmentsSource` accepts a collection of Appointment objects. Each Appointment defines the following properties:

* `Start`&mdash;Defines the value determining the start date and time of the Appointment.
* `End`&mdash;Defines the value that determing the end date and time of the appointment.
* `Subject`&mdash;Defines the value that indicate the subject of the appointment
* `IsAllDay`&mdash;Indicates whether the appointment will take all day
* `RecurrenceRule`&mdash;Defines basic properties of the recurrence rule of the appointment, for more details go to [Recurrence]({%slug recurrence-overview}) topic.


## Example

Here is a quick example on how you can create Appointments collection and bind it to the `AppointmentsSource` property of `RadScheduler`.

First, create a ViewModel class and add "Appointments" collection inside it:

<snippet id='scheduler-appointments-viewmodel' />

Add the `RadScheduler` definition to the page:

<snippet id='scheduler-appointments-example' />

The last step is to set the ViewModel as a BindingContext:

<snippet id='scheduler-appointmentssource-setvm' />

## See Also

- [Appointment Template]({%slug scheduler-appointment-template%})
