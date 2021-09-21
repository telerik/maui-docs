---
title: Configuration
page_title: .NET MAUI NumericInput Documentation | Configuration
description: Check our &quot;Configuration&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 2
slug: numericinput-configuration
---

# Configuration options 

This article will explain all configuration options that NumericInput control provides.

## Numeric Value

* `Value`(*double?*) property allows you to set a predefined value that will be presented by the control.

### Example

NumericInput definition in xaml with the `Value` property set:

```XAML
<telerikInput:RadNumericInput x:Name="numericInput" Value="12" />
```

Add the namespace: 

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

And the result:

![NumericInput Value](images/numericinput-value.png)

## Null Value Support

The `Value` property is of type nullable double, which enables the NumericInput control to accept null value as well.

### Example

```XAML
<telerikInput:RadNumericInput x:Name="numericInput" Value="{x:Null}" />
```

Add the namespace: 

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

And the result:

![NumericInput Null Value](images/numericinput-null-value.png)

## Input Range

You can restrinct the input using the `Minimum` and `Maximum` properties:

* `Minimum`(*double*): The minimum value that can be insert in the numeric input.
* `Maximum`(*double*): The maximum value that can be insert in the numeric input.

### Example

```XAML
<telerikInput:RadNumericInput x:Name="numericInput" Minimum="-5" Maximum="15" />
```

Add the namespace: 

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

And the result:

![NumericInput Minimum Maximum Values](images/numeric-min-max-values.gif)

## Step for Increment and Decrement value 

The `Step` property defines the value step that will be applied to the input value upon each decrease/increase action. The default step is 1.

### Example

```XAML
<telerikInput:RadNumericInput x:Name="numericInput" Step="10" />
```

Add the namespace: 

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```
And the result:

![NumericInput Step Feature](images/numericinput-step-feature.gif)

## See Also

- [Globalization]({%slug numericinput-globalization%})
- [Commands]({%slug numericinput-commands%})
