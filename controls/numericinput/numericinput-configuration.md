---
title: Configuration
page_title: .NET MAUI NumericInput Documentation | Configuration
description: Check our &quot;Configuration&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 2
slug: numericinput-configuration
---

# Configuration Options

This article will explain all configuration options that NumericInput control provides.

## Numeric Value

The NumericInput provides the `Value`(`double?`) property, which allows you to set a predefined value that will be presented by the control.

The following example demonstrates how to use `Value`.

1. Define the NumericInput in XAML with the `Value` property set:

 ```XAML
<telerikInput:RadNumericInput x:Name="numericInput" Value="12" />
 ```

1. Add the namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```


The following image shows the end result.

![NumericInput Value](images/numericinput-value.png)

## Null Value Support

The `Value` property is of type nullable double, which enables the NumericInput control to accept `null` values as well.

The following example demonstrates how to set the `Value` property to accept `null` values.

1. Define the NumericInput.

 ```XAML
<telerikInput:RadNumericInput x:Name="numericInput" Value="{x:Null}" />
 ```

1. Add the namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```


The following image shows the result:

![NumericInput Null Value](images/numericinput-null-value.png)

## Input Range

You can restrict the input using the `Minimum` and `Maximum` properties:

* `Minimum`(`double`)&mdash;The minimum value that can be insert in the numeric input.
* `Maximum`(`double`)&mdash;The maximum value that can be insert in the numeric input.

The following example demonstrates ho to set a range.

1. Define the NumericInput.

 ```XAML
<telerikInput:RadNumericInput x:Name="numericInput" Minimum="-5" Maximum="15" />
 ```

1. Add the namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```


The following image shows the end result:

![NumericInput Minimum Maximum Values](images/numeric-min-max-values.gif)

## Step for Increment and Decrement value

The `Step` property defines the value step that will be applied to the input value upon each decrease/increase action. The default step is 1.

The following example demonstrates how to set a step.

1. Define the NumericInput.

 ```XAML
<telerikInput:RadNumericInput x:Name="numericInput" Step="10" />
 ```

1. Add the namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```


The following image shows the end result:

![NumericInput Step Feature](images/numericinput-step-feature.gif)

## See Also

- [Globalization]({%slug numericinput-globalization%})
- [Commands]({%slug numericinput-commands%})
