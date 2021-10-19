---
title: Getting Started
page_title: .NET MAUI Border Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI Border control and learn how to add the control to your .NET MAUI application."
position: 10
slug: border_getting_started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI Border by adding the control to your project.

At the end, you will be able to achieve the following result.

....

## Prerequisites

Before adding the Border, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#setting-up-your-microsoft-project).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#downloading-telerik-ui-for-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#installing-telerik-ui-for-maui).

## Define the Control

1. When the your .NET MAUI application is set up, you are ready to add the Border control to your page by using its definition in XAML.

 ```XAML
<telerikMauiControls:RadBorder BorderColor="Red" BorderThickness="1">
    <Label Text="Hello there" Margin="2" />
</telerikMauiControls:RadBorder>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikMauiControls="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
 ```

## See Also

- [Getting Started]({% slug maui-getting-started%})
