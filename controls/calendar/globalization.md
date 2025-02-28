---
title: Globalization
page_title: .NET MAUI Calendar Documentation - Globalization
description: Check our &quot;Localization and Globalization&quot; documentation article for Telerik Calendar for .NET MAUI
position: 16
slug: calendar-globalization
---

# .NET MAUI Calendar Globalization

Globalization refers to developing an application in such a way that it works on the target device culture. This includes changes in the Calendar day names and first day of week.

The Telerik UI for <a href="https://www.telerik.com/maui-ui/calendar" target="_blank">.NET MAUI Calendar</a> control supports globalization through the `Culture` property (of type `System.Globalization.CultureInfo`).

The following example demonstrates how to set the desired culture in the `RadCalendar`:

**1.** Define the `RadCalendar` in XAML:

<snippet id='calendar-culture'/>

**2.** Add the namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Set the desired culture in the code-behind:

<snippet id='calendar-setting-culture'/>

This is the result:

![.NET MAUI Calendar Globalization](images/calendar-globalization.png)

> For a runnable example demonstrating how to configure the Calendar Culture, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Features** category.

## See Also

- [Navigation]({%slug calendar-navigation%})
- [Display modes]({%slug calendar-display-modes%})
- [Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%}) 
- [Events]({%slug calendar-events%})
- [Commands]({%slug calendar-commands%})
- [Templates]({%slug calendar-templates-overview%})
- [Styling]({%slug calendar-header-styling%})