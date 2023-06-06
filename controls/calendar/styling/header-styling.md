---
title: Header Styling
page_title: .NET MAUI Calendar Documentation - Header Styling
description: "Review what are the styling options the Telerik Calendar for .NET MAUI control provides for its header."
position: 1
slug: calendar-header-styling
---

# .NET MAUI Calendar Header Styling

The following article explais the styling options for Calendar Header:

## Styling the border of the header and label

Style the border around the Calendar Header by using the `HeaderBorderStyle`(of type `Style` with target type `telerik:RadBorder`).

Style the label in the header by using the `HeaderLabelStyle`(of type `Style` with target type `Label`).

**Example**

Calendar definition:

<snippet id='calendar-headerlabel-styling'/>

And the style for `HeaderBorderStyle`:

<snippet id='calendar-headerborder-style'/>

and for `HeaderLabelStyle`:

<snippet id='calendar-headerlabel-style'/>

![.NET MAUI Calendar Header Style](images/combobox-drop-down-style.png)

> For the Calendar Header Buttons Styling example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Styling category.

## Styling the navigation buttons

Style the navigation buttons by using the following properties:

* `NavigateToPreviousViewButtonStyle`(of type `Style` with target type `Button`)&mdash;Specifies the style for button in the header that navigates to the previous view.
* `NavigateToNextViewButtonStyle`(of type `Style` with target type `Button`)&mdash;Specifies the style for button in the header that navigates to the next view.

**Example**

Calendar definition:

<snippet id='calendar-headerbuttons-styling'/>

And the style for `NavigateToPreviousViewButtonStyle`:

<snippet id='calendar-navigatetopreviousbutton-style'/>

and for `NavigateToNextViewButtonStyle`:

<snippet id='calendar-navigatetonextbutton-style'/>

![.NET MAUI Calendar Navigation buttons Style](images/combobox-drop-down-style.png)

> For the Calendar Header Buttons Styling example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Styling category.

## See Also
