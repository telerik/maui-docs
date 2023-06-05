---
title: Globalization
page_title: .NET MAUI Calendar Documentation - Globalization
description: Check our &quot;Localization and Globalization&quot; documentation article for Telerik Calendar for .NET MAUI
position: 16
slug: calendar-globalization
---

# .NET MAUI Calendar Globalization

Globalization refers to developing an application in such a way that it works with respect to the target device culture. This includes changes in the Calendar day names and first day of week.

The Telerik UI for .NET MAUI Calendar control supports globalization through the `Culture` property(of type `System.Globalization.CultureInfo`).

**Globalization Example with RadCalendar**

Define the `RadCalendar` in XAML:

<snippet id='calendar-culture'/>

Add the namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

Set the desired culture in code-behind:

<snippet id='calendar-setting-culture'/>

This is the result:

![.NET MAUI Calendar Globalization](images/numeric_features_globalization_2.png)

> For the Calendar Culture example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Features category.

## See Also

- [Navigation]({%slug calendar-navigation%})
- [Display modes]({%slug calendar-display-modes%})
- [Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%}) 
- [Events]({%slug calendar-events%})
- [Commands]({%slug calendar-commands%})
- [Templates]({%slug calendar-templates-overview%})
- [Styling]({%slug calendar-header-styling%})