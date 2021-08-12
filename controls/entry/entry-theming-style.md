---
title: Styling
page_title: .NET MAUI Entry Documentation | Styling
description: Check our &quot;Styling&quot; documentation article for Telerik Entry for .NET MAUI control.
position: 5
slug: entry-theming-style
---

# Styling

## BorderStyle

The **BorderStyle**(*of type Telerik.XamarinForms.Input.BorderStyle*) property allows you to customize the border around the Entry through the following properties: 

* **BorderColor**(*Color*), 
* **BorderThickness**(*Thickness*) 
* **CornerRadius**(*double*)

You could define the **BorderStyle** in the Resources of your page as shown in the example below:

```XAML
<telerikInput:BorderStyle x:Key="EntryBorderStyle" BorderThickness="1" BorderColor="#4488F6" CornerRadius="8" />
```

And then apply that Style to the Entry instance:

```XAML
<telerikInput:RadEntry x:Name="entry" WatermarkText="First Name" BorderStyle="{StaticResource EntryBorderStyle}"/>
```

## See Also

- [Key Features]({% slug entry-key-features%})
- [Events]({% slug entry-events%})
