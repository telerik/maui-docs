---
title: How-to Loading Button
page_title: .NET MAUI TemplatedButton Documentation - Loading Button
description: Learn what visual elements are displayed by the Telerik UI for .NET MAUI TemplatedButton, and see how these elements build the visual structure of the control.
position: 0
slug: templatedbutton-loading-button
---

# How to Create a Loading Button

This article explains how to define a loading button using the Telerik .NET MAUI TemplatedButton. The loading indicator displays inside the button content when clicking on the button. 

The following gif shows the loading button:

![.NET MAUI TemplatedButton Loading Button](images/templatedbutton-visual-structure.png "Loading Button")

## Solution

In order to create a loading button, use a `RadTemplatedButton` with a `ContentTemplate`. Then inside the `ContentTemplate` define a `RadBusyIndicator`.

**1.** Define the button in XAML:

<snippet id='templatedbutton-loadingbutton' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel`:

<snippet id='loadingbutton-viewmodel' />

## See Also

- [.NET MAUI TemplatedButton Product Page](https://www.telerik.com/maui-ui/templatedbutton)
- [.NET MAUI TemplatedButton Forum Page](https://www.telerik.com/forums/maui?tagId=2057)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
