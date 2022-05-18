---
title: Globalization
page_title: .NET MAUI MaskedEntry Documentation | Globalization
description: "Learn how to adapt the Telerik UI for .NET MAUI MaskedEntry to device cultures by utilizing its globalization support options."
position: 8
slug: maskedentry-globalization
---

# Globalization

Globalization refers to developing an application in such a way that it works with respect to the target device culture. This includes number formatting which can vary between cultures, especially for some specific symbols, such as decimal separators, currency and other.

The Telerik UI for .NET MAUI NumericMaskedEntry control supports globalization.

**Globalization Example with NumericMaskedEntry**

Define the `NumericMaskedEntry` in XAML:

<snippet id='numericmaskedentry-globalization-xaml' />

Set the desired culture in code-behind:

<snippet id='numericmaskedentry-globalization' />

Add the namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

> For the MaskedEntry Culture example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to MaskedEntry -> Features category.

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Mask]({%slug maskedentry-mask%})
- [Validation]({%slug maskedentry-validation%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Events]({%slug maskedentry-events%})
