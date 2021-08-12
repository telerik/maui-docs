---
title: Getting Started
page_title: Getting Started with .NET MAUI Entry Control
description: Check our &quot;Getting Started&quot; documentation article for Telerik Entry for .NET MAUI control.
position: 1
slug: entry-getting-started
---

# Getting Started

## Define RadEntry control

```C#
var entry = new RadEntry();
```

In addition to this you need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Compatibility"
```

Register a renderer inside the `ConfigureMauiHandlers` method of the **Startup.cs** file of your project:

```C#
.ConfigureMauiHandlers(handlers => {

    // renderer for Telerik UI for MAUI Entry control
    handlers.AddCompatibilityRenderer(typeof(Telerik.XamarinForms.Input.RadButton), typeof(InputRenderer.ButtonRenderer));
    .....                    
```

Here is the result:

![Entry Getting Started Example](images/entry_getting_started.png)

## See Also

- [Key Features]({% slug entry-key-features%})
- [Events]({% slug entry-events%})
- [Styling]({% slug entry-theming-style%})
