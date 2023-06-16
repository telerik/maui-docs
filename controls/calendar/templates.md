---
title: Templates
page_title: .NET MAUI Calendar Documentation - Templates
description: Learn how to use the Templates ot the Telerik Calendar control for .NET MAUI.
position: 1
slug: calendar-templates-overview
---

# .NET MAUI Calendar Templates

If the default templates of the control do not suit your needs, you can easily define custom ones. The available templates for customizing are:

* `DayTemplate `(`DataTemplate`)&mdash;Specifies the content templates for the days in the month view of the Calendar.
* `MonthTemplate `(`DataTemplate`)&mdash;Specifies the content templates for the months in the year view of the Calendar.
* `YearTemplate `(`DataTemplate`)&mdash;Specifies the content templates for the years in the decade view of the Calendar.
* `DecadeTemplate `(`DataTemplate`)&mdash;Specifies the content templates for the decades in the century view of the Calendar.

## Day Template

<snippet id='calendar-templates-daytemplate-usage'/>

And the template definition

<snippet id='calendar-templates-daytemplate-definition'/>

![.NET MAUI Calendar Day Template](images/calendar-day-template.png)

## Month Template

<snippet id='calendar-templates-monthtemplate-usage'/>

And the template definition

<snippet id='calendar-templates-monthtemplate-definition'/>

![.NET MAUI Calendar Month Template](images/calendar-month-template.png)

## Year Template

<snippet id='calendar-templates-yeartemplate-usage'/>

And the template definition

<snippet id='calendar-templates-yeartemplate-definition'/>

![.NET MAUI Calendar Year Template](images/calendar-year-template.png)

## Decade Template

<snippet id='calendar-templates-decadetemplate-usage'/>

And the template definition

<snippet id='calendar-templates-decadetemplate-definition'/>

![.NET MAUI Calendar Decade Template](images/calendar-decade-template.png)

## Template Selectors

You can easy apply a template selector the calendar templates as they are of type `DataTemplate`. 

The following example demonstrates a DayTemplate that uses a Template Selector.

<snippet id='calendar-templates-templateselector-usage'/>

And the template selectors definition

<snippet id='calendar-templates-templateselector-definition'/>

And the Template Selector logic:

<snippet id='calendar-templates-custom-templateselector'/>

![.NET MAUI Calendar Template Selector](images/calendar-template-selector.png)

>important For the Calendar Templates examples refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) Calendar -> Templates category.

## See Also

- [Navigation Between the Different Views]({%slug calendar-navigation%})
- [Specify the Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%})
- [Use the exposed Commands]({%slug calendar-commands%})
- [Calendar Header Styling]({%slug calendar-header-styling%})