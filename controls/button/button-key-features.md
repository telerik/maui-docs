---
title: Key Features
page_title: .NET MAUI Button Documentation | Key Features for .NET MAUI Button
description: Check our &quot;Key Features&quot; documentation article for Telerik Button for .NET MAUI.
position: 2
tags: .net maui, telerik .net maui, ui for .net maui, button, microsoft .net maui
slug: button-key-features
---

# Key Features

The purpose of this help article is to show you the key features of the **RadButton** control. 

## Define RadButton

Add RadButton definition in XAML:

```XAML
<telerikInput:RadButton Text="RadButton" BackgroundColor="Transparent" BorderColor="Red" BorderThickness="2"/>
```

Add the following namespace: 

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
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

## Content Alignment

RadButton exposes **HorizontalContentAlignment** and **VerticalContentAlignment** properties of type Microsoft.Maui.TextAlignment which you can use to set different positioning of its content. 

Here is a quick example how you can apply these:

```XAML
<telerikInput:RadButton Text="Click me!"  
                        BorderColor="#4488F6" 
                        HorizontalContentAlignment="End" 
                        VerticalContentAlignment="Start" />
```


## Border Thickness

The **BorderThickness** property is of type Microsoft.Maui.Thickness and is used to set the borders’ width. Type Thickness gives you the option to define different border on each side of the Button.

The snippet below demonstrates how BorderThickness could be defined.

```XAML
<telerikInput:RadButton Text="Click me!"  
                        BorderThickness="6, 2, 2, 6" 
                        BorderColor="#4488F6" />
```

#### Telerik Button for .NET MAUI

![Button Key Features Example](images/button-key-features.png)

## See Also

- [Circular Button]({%slug button-howto-create-circle-button%})
