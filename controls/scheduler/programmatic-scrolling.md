---
title: Programmatic Scrolling
page_title: .NET MAUI Scheduler Documentation - Programmatic Scrolling
description: Learn more about the programmatic scrolling feature in the Telerik UI for .NET MAUI Scheduler control.
position: 
slug: scheduler-programmating-scrolling 
---

# Programmatic Scrolling

The Telerik UI for .NET MAUI Scheduler provides an option for programmatic scrolling. The option allows you to set up the `RadScheduler`, so that the view is scrolled to specific time or a particular appointment. This can be achieved with the `ScrollIntoView` method. The method have two overloads.

## Scroll Into Time

`ScrollIntoView` method scrolls the current View to the specified time. It accept a single parameter of type `TimeOnly`. The snippet below shows how the method can be used:

 <snippet id='scheduler-scrolltotime-code' />

The result from the code snippet:

![.NET MAUI Scheduler Scroll Into View](images/)

## Scroll Into Appointment

`ScrollIntoView` method allows you to configure the current View to scroll down and display the specified as a parameter appointment. The snippet below on how this method can be used:

 <snippet id='scheduler-scrolltoapp-code' />

The result from the code snippet:

![.NET MAUI Scheduler Scroll Into View](images/)

## See Also

- 
- 
- 
- 