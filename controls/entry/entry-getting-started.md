---
title: Getting Started
page_title: Getting Started with .NET MAUI Entry Control
description: Check our &quot;Getting Started&quot; documentation article for Telerik Entry for .NET MAUI control.
position: 1
slug: entry-getting-started
---

# Getting Started

## Define RadEntry control

```XAML
<telerikInput:RadEntry x:Name="entry" 
					   WatermarkText="Enter first name"/>
```

In addition to this you need to add the following namespace:

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

Here is the result:

![Entry Getting Started Example](images/entry_getting_started.png)

## See Also

- [Text Appearance]({% slug entry-text-appearance%})
- [Events]({% slug entry-events%})
- [Styling]({% slug entry-styling%})
