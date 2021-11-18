---
title: Getting Started
page_title: NET MAUI SegmentedControl Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI SegmentedControl and add the control to your .NET MAUI project."
position: 1
slug: segmentedcontrol-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI SegmentedControl by adding the control to your project.

At the end, you will be able to achieve the following result.

..........

## Prerequisites

Before adding the SegmentedControl, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a SegmentedControl control to your page.

 ```XAML
<telerikInput:RadSegmentedControl x:Name="segmentControlText"
								  HeightRequest="60"
                                  VerticalOptions="Start">
    <telerikInput:RadSegmentedControl.ItemsSource>
        <x:Array Type="{x:Type x:String}">
            <x:String>Popular</x:String>
            <x:String>Library</x:String>
            <x:String>Playlists</x:String>
            <x:String>Friends</x:String>
        </x:Array>
    </telerikInput:RadSegmentedControl.ItemsSource>
</telerikInput:RadSegmentedControl>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Compatibility"
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

- [Selection]({%slug segmentedcontrol-features-selection%})
- [Disabled Segments]({%slug segmentedcontrol-features-disable-segment%})
