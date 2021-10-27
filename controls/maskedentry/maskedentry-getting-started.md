---
title: Getting Started
page_title: .NET MAUI MaskedInput Documentation | Getting Started
description: Check our &quot;Getting Started&quot; documentation article for Telerik MaskedInput for .NET MAUI control.
position: 1
slug: maskedentry-getting-started
---

# Getting Started

This guide demonstrates how to add Telerik UI for .NET MAUI MaskedEntry control to your application. 

At the end, you will be able to achieve the following result:

![Regex Masked Entry Picker Getting Started](images/maskedentry-getting-started.png)

## Prerequisites

Before adding the MaskedEntry, first you need to [setup your .NET MAUI app]({%slug maui-getting-started %}#set-up-your-net-maui-application), and [download]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui) and [install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define RadMaskedEntry control

1. When the app is setup, you are ready to add a RadMaskedEntry control to your page. The example demonstrates the definition of the `RadRegexMaskedEntry` with `Mask` and `PlaceholderText` properties applied

 ```XAML
<telerik:RadRegexMaskedEntry x:Name="regexMaskedEntry" Mask="^[a-z]$" PlaceholderText="^[a-z]$" />
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
 ```
 
## See Also

- [Masked Types]({%slug maskedentry-masked-types%})
- [Events]({%slug maskedentry-events%})