---
title: Header Text Formatting
page_title: .NET MAUI Calendar Documentation - Header Text Formatting
description: Learn how to format the header text of the Telerik UI for .NET MAUI Calendar control.
position: 9
slug: calendar-date-formatting
---

# .NET MAUI Calendar Header Text Formatting

The .NET MAUI Calendar allows you to specify the format of the header label text in the different display modes. The format must be a valid date format. The available options for the header label text formatting are: 

* `MonthHeaderTextFormat`(`string`)&mdash;Specifies the format of the header text when the Calendar `DisplayMode` is `Month`.
* `YearHeaderTextFormat`(`string`)&mdash;Specifies the format of the header text when the Calendar `DisplayMode` is `Year`.
* `DecadeHeaderTextFormat`(`string`)&mdash;Specifies the format of the header text when the Calendar `DisplayMode` is `Decade`.
* `CenturyHeaderTextFormat`(`string`)&mdash;Specifies the format of the header text when the Calendar `DisplayMode` is `Century`.

## Header Text Format Example

The following example demonstrates how to define a Calendar and format the header text with the `MonthHeaderTextFormat`, `YearHeaderTextFormat`, `DecadeHeaderTextFormat`, and `CenturyHeaderTextFormat` properties:

<snippet id='calendar-headertext-formatting'/>

## See Also

- [Navigation]({%slug calendar-navigation%})
- [Display modes]({%slug calendar-display-modes%})
- [Selection modes]({%slug calendar-selection%}) 
- [Events]({%slug calendar-events%})
- [Commands]({%slug calendar-commands%})
- [Templates]({%slug calendar-templates-overview%})
- [Styling]({%slug calendar-header-styling%})