---
title: Centering the Popup in .NET MAUI Applications
description: Learn how to ensure a Popup is always displayed in the center of the screen in .NET MAUI applications using the Telerik UI for MAUI Popup control.
type: how-to
page_title: How to Ensure a Popup is Centered in .NET MAUI
slug: centering-popup-dotnet-maui
tags: popup, .net maui, center, placement, ui, telerik
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI Popup | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

When using the Telerik UI for MAUI [Popup](https://docs.telerik.com/devtools/maui/controls/popup/overview) control to display content, such as a calendar, it's essential to ensure the Popup is always centered on the screen, regardless of device or orientation.

This knowledge base article also answers the following questions:
- How can I center a Popup in my .NET MAUI application?
- What are the steps to always display a Popup in the center of the screen?
- Can I position a Telerik MAUI Popup in the center of the page?

## Solution

To center the Popup on the screen in a .NET MAUI application using the Telerik UI for MAUI Popup control, follow these steps:

1. Attach the Popup to the page.
2. Set the Popup's `Placement` property to `Center`. This ensures the Popup is displayed in the center of the page/screen.
3. Optionally, open the Popup on a button click or any other event as required.

Below is an example of how to implement this in a .NET MAUI application using XAML:

```XAML
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             xmlns:local="clr-namespace:YourNamespace"
             x:Class="YourNamespace.MainPage">

    <!-- Content of the page -->
    <ScrollView>
        <VerticalStackLayout>
            <!-- Your page content -->
            <Button Text="Open Popup" Clicked="Button_Clicked" />
        </VerticalStackLayout>
    </ScrollView>

    <!-- Attach the Popup to the page -->
    <telerik:RadPopup.Popup>
        <telerik:RadPopup x:Name="MyPopup" Placement="Center">
            <!-- Your Popup content -->
            <local:PopupContentView />
        </telerik:RadPopup>
    </telerik:RadPopup.Popup>
</ContentPage>
```

In this example, replace `YourNamespace` with your actual namespace, and `PopupContentView` with the content you want to display in the Popup.

## See Also

- [Popup Overview](https://docs.telerik.com/devtools/maui/controls/popup/overview)
- [Popup Placement Documentation](https://docs.telerik.com/devtools/maui/controls/popup/placement)
