---
title: Create Circle Button
page_title: .NET MAUI Button Documentation | Create Circle Button
description: Check our &quot;Create Circle Button&quot; documentation article for Telerik Button for .NET MAUI control.
position: 0
slug: button-howto-create-circle-button
---

# Create Circle Button

&nbsp;

You could easily create circular buttons with RadButton by adjusting its Width, Height and BorderRadius properties following the next instructions:

* Width should be equal to Height;
* BorderRadius should be set to half Width/Height value;


> In some cases, you may need to set a BorderWidth value in order for BorderRadius to take effect.

Here is a quick example:

```XAML
<telerikInput:RadButton WidthRequest="120" 
					    HeightRequest="120"                                
					    Text="Circle Button" 
					    FontSize="Micro" 
					    TextColor="White" 
					    BackgroundColor="DarkBlue" 
					    CornerRadius="60"  />
```

Add the namespace: 

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Compatibility"
```

How it looks:

![Button Key Features Example](../images/button-howto-circlebutton.png)

## See Also

- [Button Getting Started]({%slug maui-getting-started%})
