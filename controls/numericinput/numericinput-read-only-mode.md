---
title: Read-Only Mode
page_title: .NET MAUI NumericInput Documentation | Read-Only Mode
description: Check our &quot;Read-Only Mode&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 4
slug: numericinput-read-only-mode
---

# Read-Only Mode

RadNumericInput supports read-only mode in which the end user cannot type into the input field – **updating the value is possible only through the increase/decrease buttons**. 

* Enable the read-only mode when setting `IsReadOnly` to `True`.

## Example

NumerinInput definition in XAML with `IsReadOnly` set to `True`

```XAML
<telerikInput:RadNumericInput x:Name="numericInput" IsReadOnly="True"/>
```

Add the following namespase: 

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

And the result:

![NumericInput Read-Only mode](images/numericinput-read-only-mode.png)

## See Also

- [Globalization]({%slug numericinput-globalization%})
- [Commands]({%slug numericinput-commands%})
