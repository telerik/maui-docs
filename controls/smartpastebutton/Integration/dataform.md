---
title: Integration with DataForm
page_title: Integrating the .NET MAUI SmartPasteButton with DataForm
description: Learn how to integrate the Telerik SmartPasteButton for .NET MAUI with the DataForm control to populate form fields with structured data extracted from unstructured text.
position: 1
slug: smartpastebutton-dataform-integration
---

# .NET MAUI SmartPasteButton Integration with DataForm

The SmartPasteButton control is designed to work in conjunction with the DataForm control, allowing you to easily populate form fields with structured data extracted from unstructured text. By integrating the SmartPasteButton with the DataForm, you can enhance the user experience and streamline data entry processes within your application.

To integrate the SmartPasteButton with the DataForm, you need to set the `Provider` property of the SmartPasteButton to reference the DataForm instance. This allows the SmartPasteButton to extract structured information from the clipboard content and populate the corresponding fields in the DataForm based on the form structure.

This is an example of how to set the `Provider` property of the SmartPasteButton to reference a DataForm instance in XAML:

```XAML
<telerik:RadDataForm x:Name="dataForm" ... />

<telerik:RadSmartPasteButton Provider="{x:Reference dataForm}" ... />
```

This is an example with SmartPasteButton and DataForm:

**1.** Define the DataForm and the SmartPasteButton controls on the page:

<snippet id='smartpastebutton-gettingstarted-xaml' />

**2.** Add the DataForm control to your page. The SmartPasteButton is designed to work in conjunction with the DataForm control, allowing you to easily populate form fields with structured data extracted from unstructured text. By integrating the SmartPasteButton with the DataForm, you can enhance the user experience and streamline data entry processes within your application.

<snippet id='smartpastebutton-gettingstarted-dataform-xaml' />

**3** For the demo, a text from the clipboard will be used for the smart paste operation.

<snippet id='smartpastebutton-gettingstarted-copy-xaml' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**5.** The copy button's `Clicked` event handler:

<snippet id='smartpaste-gettingstarted-copy' />

**6.** The `SmartPasteRequest` event handler:

<snippet id='smartpaste-gettingstarted-paste-request' />

![.NET MAUI SmartPasteButton Getting Started](../images/smartpastebutton-default-look.gif)

>important The SmartPasteButton examples in the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) use a Telerik-hosted AI service for demonstration purposes only. 
>
>To use the smart paste functionality in your application, you must configure your own AI service.
>
>How to do that is described in the [Configuration]({%slug smartpastebutton-configuration%}) article.

> For a runnable example with the SmartPasteButton Integration with DataForm, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **SmartPasteButton > Getting Started**.

## See Also

- [Styling the SmartPasteButton]({%slug smartpastebutton-styling%})
- [Visual States of the SmartPasteButton]({%slug smartpastebutton-visual-states%})
- [Events of the SmartPasteButton]({%slug smartpastebutton-events%})
- [Configure the SmartPasteButton]({%slug smartpastebutton-configuration%})