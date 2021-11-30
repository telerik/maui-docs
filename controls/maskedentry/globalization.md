---
title: Globalization
page_title: .NET MAUI MaskedEntry Documentation | Globalization
description: "Telerik MaskedEntry for .NET MAUI has a globalization support"
position: 8
slug: maskedentry-globalization
---

# Globalization

Globalization refers to developing an application in such a way that it works with respect to the target device culture. This includes numbers formatting which can vary between cultures, especially for some specific symbols, such as decimal separators, currency and other.

Telerik UI for .NET MAUI NumericMaskedEntry control has a globalization support. 

**Globalization Example with NumericMaskedEntry**

Define the NumericMaskedEntry in XAML:

<snippet id='numericmaskedentry-globalization-xaml' />

Set the desired culture in code behind:

<snippet id='numericmaskedentry-globalization' />

And the nampespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```
 
>tip Culture example can be found in the MaskedEntry/Features folder of the [SDK .NET MAUI Application]({%slug maui-demo-app%}).

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Mask]({%slug maskedentry-mask%})
- [Validation]({%slug maskedentry-validation%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Events]({%slug maskedentry-events%})
