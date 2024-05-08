---
title: Getting Started
page_title: .NET MAUI ComboBox Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI ComboBox and add the control to your .NET MAUI project.
position: 1
slug: combobox-getting-started
---

# Getting Started with the .NET MAUI ComboBox

This guide provides the information you need to start using the [Telerik UI for .NET MAUI ComboBox]({%slug combobox-overview%}) by adding the control to your project.

At the end, you will achieve the following result.

![ComboBox Getting Started](images/combobox-getting-started.png)

## Prerequisites

Before adding the ComboBox, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

1. [Register Required Handlers]({%slug maui-getting-started %}#step-4-register-required-handlers).

## Define the Control

When your .NET MAUI application is setup, you are ready to add a ComboBox control to your page. The following example demonstrates the definition of the `RadComboBox` with `ItemsSource` set to a static collection as well as bound to property from a ViewModel class.

### Using Static Data

<snippet id='combobox-getting-started-static-items-xaml'/>

Here is the result:

![ComboBox Getting Started](images/combobox-getting-started.png)

### Binding to a Complex Object

**1.** Define the ComboBox in XAML:

<snippet id='combobox-getting-started-complex-object-xaml'/>

> When binding to a complex objects, ComboBox **DisplayMemberPath** property needs to be set.

**2.** Define a sample business model:

<snippet id='combobox-city-businessmodel'/>

**3.** Add the ViewModel:

<snippet id='combobox-cities-viewmodel'/>

Here is the result:

![ComboBox Binding](images/combobox-getting-started-complex-data.png)

>important For the ComboBox Getting Started example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Additional Resources

- [.NET MAUI ComboBox Product Page](https://www.telerik.com/maui-ui/checkbox)
- [.NET MAUI ComboBox Forum Page](https://www.telerik.com/forums/maui?tagId=1937)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Data Binding]({%slug combobox-databinding%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})
