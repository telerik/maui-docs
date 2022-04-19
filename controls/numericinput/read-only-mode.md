---
title: Read-Only Mode
page_title: .NET MAUI NumericInput Documentation | Read-Only Mode
description: Check our &quot;Read-Only Mode&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 4
previous_url: /controls/numericinput/numericinput-read-only-mode
slug: numericinput-read-only-mode
---

# Read-Only Mode

The NumericInput supports read-only mode in which the end user cannot type into the input field. Updating the value is possible only through the **Increase** and **Decrease** buttons.

To enable the read-only mode, set `IsReadOnly` to `True`.

Define the NumericInput in XAML with `IsReadOnly` set to `True`.

```XAML
<telerikInput:RadNumericInput x:Name="numericInput" IsReadOnly="True"/>
```

Add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

The following image shows the result:

![NumericInput Read-Only mode](images/numericinput-read-only-mode.png)

## See Also

- [Globalization]({%slug numericinput-globalization%})
- [Commands]({%slug numericinput-commands%})
