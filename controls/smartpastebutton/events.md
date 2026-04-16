---
title: Events
meta_title: .NET MAUI SmartPasteButton Documentation - Events
description: Review the SmartPasteButton event that is raised when the RadSmartPasteButton initiates a smart paste operation.
position: 7
slug: smartpastebutton-events
---

# .NET MAUI SmartPasteButton Events

The .NET MAUI SmartPasteButton exposes the following event:

* `SmartPasteRequest`&mdash;Raised when the `RadSmartPasteButton` initiates a smart paste operation. The `SmartPasteRequest` event handler receives two parameters:
	* The `sender` argument which is of type `RadSmartPasteButton`.
	* A `SmartPasteButtonRequestContext` object which contains the clipboard content, fields, a cancellation token, and methods to signal the result of the AI request.

## Using the SmartPasteRequest Event

The following example demonstrates how to use the `SmartPasteRequest` event.

**1.** Define the button in XAML:

<snippet id='smartpastebutton-gettingstarted-xaml' />

**2.** Add the DataForm control to your page. The SmartPasteButton is designed to work with the DataForm control, allowing you to populate form fields with structured data extracted from unstructured text. By integrating the SmartPasteButton with the DataForm, you can enhance the user experience and streamline data entry processes within your application.

<snippet id='smartpastebutton-gettingstarted-dataform-xaml' />

**3.** Text from the clipboard is used for the smart paste operation.

<snippet id='smartpastebutton-gettingstarted-copy-xaml' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**5.** The copy button's `Clicked` event handler:

<snippet id='smartpaste-gettingstarted-copy' />

**6.** The `SmartPasteRequest` event handler:

<snippet id='smartpaste-gettingstarted-paste-request' />

This is the result:

![.NET MAUI SmartPasteButton Event](images/smartpastebutton-default-look.gif)

>important The SmartPasteButton examples in the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) use a Telerik-hosted AI service for demonstration purposes only. 
>
>To use the smart paste functionality in your application, you must configure your own AI service.
>
>How to do that is described in the [Configuration]({%slug smartpastebutton-getting-started%}#step-1-configure-the-ai-service) article.

> For a runnable example demonstrating the SmartPasteButton `SmartPasteRequest` event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **SmartPasteButton > Getting Started** category.

## See Also

- [Configure the SmartPasteButton]({%slug smartpastebutton-configuration%})
- [Set Visual States]({%slug smartpastebutton-visual-states%})
- [Execute Command]({%slug smartpastebutton-command%})
- [Style the SmartPasteButton]({%slug smartpastebutton-styling%})