---
title: Value
page_title: .NET MAUI MaskedEntry Documentation | Value
description: "Try now the Telerik MaskedEntry for .NET MAUI formatting and restricting text to predefined patterns, and providing input validation and masks."
position: 4
slug: maskedentry-value
---

# Value

If you want to have a prefedfined values inside the MAskedEntry, set the `Value`(`string`) property. It returns the user input without the formatting characters. 

**Example with RadTextMaskedEntry with Value property**

<snippet id='textmaskedentry-value-xaml' />
```C#
this.textMaskedEntry.Value = "Test";
```

And the namespace used:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

## Null Value Support

By default the MaskedEntry control doesn't allow you to set `null` to its `Value` property. To allow null values you have to set the `AllowNullValue` property to `True`.

**Example for Null Value with RadNumericMaskedEntry**

<snippet id='numericmaskedentry-allownullvalues-true-xaml' />

And the namespace used:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

>tip AllowNullValues eample can be found in the MaskedEntry/Features folder of the [SDK MAUI Application]({%slug maui-demo-app%}).

## See Also

