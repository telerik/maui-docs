---
title: Getting Started
page_title: .NET MAUI DockLayout Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI DockLayout and add the control to your .NET MAUI project."
position: 1
slug: docklayout-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI DockLayout by adding the control to your project.

At the end, you will be able to achieve the following result.

![RadDockLayout](images/docklayout_getting_started.png)

## Prerequisites

Before adding the DockLayout, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When the your .NET MAUI application is set up, you are ready to add a Barcode control to your page.

<snippet id='docklayout-getting-started-xaml' />
 ```XAML
<telerik:RadDockLayout x:Name="dockLayout">
    <Grid HeightRequest="60"
          BackgroundColor="#009688"
          telerik:RadDockLayout.Dock="Top">
        <Label Margin="20" Text="Title"/>
    </Grid>
    <Grid BackgroundColor="#659BFC"
          telerik:RadDockLayout.Dock="Left">
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto"/>
        </Grid.ColumnDefinitions>
        <Label Margin="20" Text="Navigation" />
    </Grid>
    <Grid BackgroundColor="#1455C9"
          telerik:RadDockLayout.Dock="Bottom">
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
        </Grid.RowDefinitions>
        <Label Margin="20" Text="Bottom" />
    </Grid>
    <Grid  BackgroundColor="#FCCFB0">
        <Label Margin="20" Text="Content" />
    </Grid>
</telerik:RadDockLayout>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the `Startup.cs` file of your project:

 ```C#
using Telerik.Maui.Controls.Compatibility;

public void Configure(IAppHostBuilder appBuilder)
{
	appBuilder		
		.UseTelerik()
		.UseMauiApp<App>();

}              
 ```

## See Also

* [Docking Functionality]({% slug docklayout-docking %})
