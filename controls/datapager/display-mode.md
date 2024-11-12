---
title: Display Mode
page_title: .NET MAUI DataPager Documentation - Display Mode
description: Learn what are the different options to display buttons in the .NET MAUI DataPager control.
position: 5
slug: datapager-display-mode
tags: display mode
---

# .NET MAUI DataPager Display Mode

The DataPager lets you control the visibility of its visual elements. In addition, you can use Adaptive Display modes to arrange the pager's elements.

To define which elements can be displayed in the DataPager, use the `DisplayMode` (`enum` of type `Telerik.Maui.Controls.DataPager.DataPagerDisplayMode`) property. The available options are:

* `None`&mdash;Displays no elements in the DataPager.
* `FirstPageButton`&mdash;Displays the first page button.
* `PrevPageButton`&mdash;Displays the previous page button.
* `NumericButtons`&mdash;Displays the numeric buttons.
* `NavigationComboBox`&mdash;Displays the navigation ComboBox.
* `NextPageButton`&mdash;Displays the next page button.
* `LastPageButton`&mdash;Displays the last page button.
* `PageSizesView`&mdash;Displays the `PageSizes` view.
* `NavigationView`&mdash;Displays the navigation view.

>tip The `DisplayMode` property supports a bitwise combination of the values from the `DataPagerDisplayMode` enumeration to enable more than one option.

The following example demonstrates how to use the  `DisplayMode` property:

**1.** Define the DataPager in XAML:

<snippet id='datapager-display-mode' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel`:

<snippet id='datapager-features-viewmodel' />

This is the result on desktop:

![.NET MAUI DataPager Display mode](images/datapager-displaymode.gif)

> For the DataPager Display Mode example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataPager > Features** category.

## Adaptive Display Modes

The DataPager lets you customize the default arrangement of the elements in the pager by providing the `AdaptiveDisplayModes` property:

* `AdaptiveDisplayModes` (`IList<DataPagerDisplayMode>`)&mdash;Specifies a list of the desired combinations of elements that should be displayed. The actual elements that will be displayed are the result of the DataPager's `DisplayMode` property, and the size of the control.

For example, if you set `AdaptiveDisplayModes` and `DisplayMode` to the values in the snippet below, the DataPager will arrange the elements based on the values set in the `AdaptiveDisplayModes` collection and will skip the elements that are not defined in the `DisplayMode` property&mdash;the `NextPageButton` element.

```XAML
<telerik:RadDataPager Source="{Binding Data}"
                      DisplayMode="FirstPageButton,LastPageButton,NavigationComboBox">
    <telerik:RadDataPager.AdaptiveDisplayModes>
        <x:Array Type="{x:Type telerik:DataPagerDisplayMode}">
            <telerik:DataPagerDisplayMode>FirstPageButton, NavigationComboBox, NextPageButton, LastPageButton</telerik:DataPagerDisplayMode>
        </x:Array>
    </telerik:RadDataPager.AdaptiveDisplayModes>
</telerik:RadDataPager>
```

This is the result on WinUI:

![.NET MAUI DataPager Display mode and AdaptiveDisplay mode](images/datapager-displaymode-adaptivemode.png)

## Example

The following example demonstrates how to use the  `AdaptiveDisplayModes` property:

**1.** Define the DataPager in XAML:

<snippet id='datapager-adaptivedisplay-mode' />

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel`:

<snippet id='datapager-features-viewmodel' />

This is the result on desktop:

![.NET MAUI DataPager Adaptive Display mode](images/datapager-adaptive-displaymode.png)

> For the DataPager Display Mode example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataPager > Features** category.

## Additional Resources

- [.NET MAUI DataPager Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataPager Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Paged Source]({%slug datapager-data-binding%})
- [Ellipsis Modes]({%slug datapager-ellipsis-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Styling]({%slug datapager-styling%})
- [Integration with DataGrid]({%slug datapager-datagrid%})