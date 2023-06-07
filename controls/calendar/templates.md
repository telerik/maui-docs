---
title: Templates
page_title: .NET MAUI Calendar Documentation - Templates
description: Check our &quot;Templates&quot; documentation article for Telerik Calendar for .NET MAUI control.
position: 1
slug: calendar-templates-overview
---

# .NET MAUI Calendar Templates

If the default templates of the control do not suit your needs, you can easily define custom ones. The available templates for customizing are:

* `DayTemplate `(`DataTemplate`)&mdash;Specifies the content templates for the days in the month view of the calendar.
* `MonthTemplate `(`DataTemplate`)&mdash;Specifies the content templates for the months in the year view of the calendar.
* `YearTemplate `(`DataTemplate`)&mdash;Specifies the content templates for the years in the decade view of the calendar.
* `DecadeTemplate `(`DataTemplate`)&mdash;Specifies the content templates for the decades in the century view of the calendar.

**Exmaple with Day Template**

<snippet id='calendar-templates-daytemplate-usage'/>

And the template definition

<snippet id='calendar-templates-daytemplate-definition'/>

**Exmaple with Month Template**

<snippet id='calendar-templates-monthtemplate-usage'/>

And the template definition

<snippet id='calendar-templates-monthtemplate-definition'/>

**Exmaple with Year Template**

<snippet id='calendar-templates-yeartemplate-usage'/>

And the template definition

<snippet id='calendar-templates-yeartemplate-definition'/>

**Exmaple with Decade Template**

<snippet id='calendar-templates-decadetemplate-usage'/>

And the template definition

<snippet id='calendar-templates-decadetemplate-definition'/>

## Template Selectors

You can easily apply a template selector the the calendar templates as they are of type `DataTemplate`. 

**Example with DayTemplate using a Template Selector**

<snippet id='calendar-templates-templateselector-usage'/>

And the template selectors definition

<snippet id='calendar-templates-templateselector-definition'/>

And the Template Selector logic:

<snippet id='calendar-templates-custom-templateselector'/>

>important For the Calendar Templates examples refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) Calendar -> Templates category.

## See Also

