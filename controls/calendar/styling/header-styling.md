---
title: Header Styling
page_title: .NET MAUI Calendar Documentation - Header Styling
description: Review the styling options that the Telerik UI for .NET MAUI Calendar control provides for its header.
position: 1
slug: calendar-header-styling
---

# .NET MAUI Calendar Header Styling

The .NET MAUI Calendar component comes with built-in styling options that allow you to customize the appearance of its header.

## Styling the Header Border and Label

* To style the border around the Calendar header, use the `HeaderBorderStyle`(of type `Style` with target type `telerik:RadBorder`).

* To style the label in the header, use the `HeaderLabelStyle`(of type `Style` with target type `Label`).

The following example demonstrates how to apply custom styles to the header label and the border around the header:

**1.** Define the Calendar:

<snippet id='calendar-headerlabel-styling'/>

**2.** Add the `HeaderBorderStyle` style:

<snippet id='calendar-headerborder-style'/>

**3.** Add the `HeaderLabelStyle` style:

<snippet id='calendar-headerlabel-style'/>

![.NET MAUI Calendar Header Style](images/combobox-drop-down-style.png)

> For a runnable example that demonstrates how to style the Calendar header buttons, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Calendar > Styling**.

## Styling the Navigation Buttons

To style the navigation buttons in the header of the Calendar, use the following properties:

* `NavigateToPreviousViewButtonStyle`(of type `Style` with target type `Button`)&mdash;Specifies the style for the button in the header that navigates to the previous view.
* `NavigateToNextViewButtonStyle`(of type `Style` with target type `Button`)&mdash;Specifies the style for the button in the header that navigates to the next view.

The following example demonstrates how to apply custom styles to the navigation buttons:

**1.** Define the Calendar:

<snippet id='calendar-headerbuttons-styling'/>

**2.** Add the `NavigateToPreviousViewButtonStyle` style:

<snippet id='calendar-navigatetopreviousbutton-style'/>

**3.** Add the `NavigateToNextViewButtonStyle` style:

![.NET MAUI Calendar Navigation buttons Style](images/combobox-drop-down-style.png)

> For a runnable example that demonstrates how to style the Calendar header buttons, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Calendar > Styling**.

## See Also

- [Day Styling]({%slug calendar-day-styling%})
- [Decade Styling]({%slug calendar-decade-styling%})
- [Month Styling]({%slug calendar-month-styling%})
- [Year Styling]({%slug calendar-year-styling%})
