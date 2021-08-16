---
title: Getting Started
page_title: Getting Started with .NET MAUI CheckBox Control 
description: Check our &quot;Getting Started&quot; documentation article for Telerik CheckBox for .NET MAUI.
position: 1
slug: checkbox-getting-started
---

# Getting Started

## Define RadCheckBox control

```XAML
<telerikPrimitives:RadCheckBox x:Name="checkbox" />
```

Add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Compatibility"
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

## See Also

- [Key Features]({% slug checkbox-key-features%})