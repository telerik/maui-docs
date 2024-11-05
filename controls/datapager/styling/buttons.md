---
title: Buttons Styling
page_title: .NET MAUI DataPager Documentation - Buttons Styling
description: Learn how to style the navigation buttons and page buttons in the Telerik UI for .NET MAUI DataPager control.
position: 0
slug: datapager-styling-buttons
---

# Styling the DataPager Buttons

The DataPager for .NET MAUI provides a styling mechanism for customizing the look of the navigation and page buttons.

## Styling the Navigation Buttons

The DataPager provides a styling mechanism for customizing the look of the navigation buttons by using the following properties:

* `NavigateToFirstPageButtonStyle` (`Style` with target type of `telerik:DataPagerButton`)&mdash;Specifies the style which applies to the first page navigation button.
* `NavigateToPreviousPageButtonStyle` (`Style` with target type of `telerik:DataPagerButton`)&mdash;Specifies the style which applies to the previous page navigation button.
* `NavigateToNextPageButtonStyle` (`Style` with target type of `telerik:DataPagerButton`)&mdash;Specifies the style which applies to the next page navigaton button.
* `NavigateToLastPageButtonStyle` (`Style` with target type of `telerik:DataPagerButton`)&mdash;Specifies the style which applies to the last page navigation button.

The `DataPagerButton` inherits from `RadTemplatedButton`. Set the properties described in the [TemplatedButton Styling]({%slug templatedbutton-styling%}) article to the DataPager navigation buttons styling proepries.

The `DataPagerButton` exposes additional visual states&mdash;`Selected` adn `SelectedDisabled`. Review the [TemplatedButton Visual States]({%slug templatedbutton-visual-states%}) article to check what are the other states you can set to the navigation buttons.

## Styling the Nummeric Buttons

The DataPager provides a styling mechanism for customizing the look of the numeric buttons by using the follwoing properties:

* `NumericButtonStyle` (`Style` with target type of `telerik:DataPagerButton`)&mdash;Specifies the style which applies to the numeric buttons.
* `NumericButtonsViewStyle` (`Style` with target type of `telerik:DataPagerNumericButtonsView`)&mdash;Specifies the style which applies to the view presenting the numeric buttons. 

The `DataPagerButton` inherits from `RadTemplatedButton`. Set the properties described in the [TemplatedButton Styling]({%slug templatedbutton-styling%}) article to the DataPager navigation buttons styling proepries.

The `DataPagerButton` exposes additional visual states&mdash;`Selected` adn `SelectedDisabled`. Review the [TemplatedButton Visual States]({%slug templatedbutton-visual-states%}) article to check what are the other states you can set to the navigation buttons.

## Example

Here is an example how to style the buttons in the DataPager control.

**1.** Define the DataPager in XAML:

<snippet id='datapager-styling-buttons' />

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the buttons resources in the page's resource:

<snippet id='datapager-styling-buttons-resources' />

**4.** Define sample data:

<snippet id='datagrid-datapager-data' />

> For the DataPager Buttons styling example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataPager > Styling** category.


## See Also

- [Paged Source]({%slug datapager-data-binding%})
- [Display Modes]({%slug datapager-display-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Styling the DataPager]({%slug datapager-styling%})
- [Integration with DataGrid]({%slug datapager-datagrid%})