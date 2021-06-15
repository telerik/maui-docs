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

Register a renderer inside the `ConfigureMauiHandlers` method of the **Startup.cs** file of your project:

```C#
.ConfigureMauiHandlers(handlers => {

    // renderer for Telerik UI for MAUI CheckBox
	handlers.AddCompatibilityRenderer(typeof(Telerik.XamarinForms.Primitives.RadCheckBox), typeof(PrimitivesRenderer.CheckBoxRenderer));
    .....           
```

## See Also

- [Key Features]({% slug checkbox-key-features%})