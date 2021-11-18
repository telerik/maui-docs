---
title: Read-Only Mode
page_title: .NET MAUI Rating Documentation | Read-Only Mode
description: Check our &quot;Key Features&quot; documentation article for Telerik Rating for .NET MAUI.
position: 3
slug: rating-read-only-mode
---

# Read-Only Mode

The Rating control supports a read-only mode in which the end user cannot change its `Value` (the number of the selected items). You can enable the read-only mode through `IsReadOnly` property.

Define the `RadShapeRating` in XAML:

```XAML
<telerikInput:RadShapeRating AutomationId="readOnlyRating"
                           Value="4"
                           x:Name="radRating"
                           IsReadOnly="True"/>
 ```

Add the namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"  
```

## See Also

- [Shape Rating]({% slug rating-shape-rating %})
- [Templated Rating]({% slug rating-templated-rating %})
