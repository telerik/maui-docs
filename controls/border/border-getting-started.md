---
title: Getting Started
page_title: .NET MAUI Border Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI Border control and learn how to add the control to your .NET MAUI application."
position: 10
slug: border-getting-started 
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI Border by adding the control to your project.

At the end, you will be able to achieve the following result.

![Border Getting Started](images/border-getting-started.png)

## Prerequisites

Before adding RadBorder, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When the your .NET MAUI application is set up, you are ready to add the Border control to your page by using its definition in XAML.

 ```XAML
<telerikMauiControls:RadBorder BorderColor="#4488F6" 
								CornerRadius="5">
    <Label Text="Hello there" Margin="2" />
</telerikMauiControls:RadBorder>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikMauiControls="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
 ```

## See Also

- [Setting the Color of the Border]({%slug border-styling %}#border-color)
- [Setting the Border Thickness]({% slug border-styling%}#border-thickness)
- [Configuring the Corner Radius of the Border]({% slug border-corner-radius %})
