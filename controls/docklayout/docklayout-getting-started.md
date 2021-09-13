---
title: Getting Started
page_title: Getting Started with .NET MAUI DockLayout Control
description: Check our &quot;Getting Started&quot; documentation article for Telerik DockLayout for .NET MAUI control.
position: 1
slug: docklayout-getting-started
---

# Getting Started

## Define RadDockLayout control

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

In addition to this you need to add the following namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

Register the Telerik controls through `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the **Startup.cs** file of your project:

```C#
using Telerik.Maui.Controls.Compatibility;

public void Configure(IAppHostBuilder appBuilder)
{
	appBuilder		
		.UseTelerik()
		.UseMauiApp<App>();
		
}              
```

This is the result:

![RadDockLayout](images/docklayout_getting_started.png)

## See Also

- [Docking Functionality]({% slug docklayout-docking%})