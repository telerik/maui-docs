---
title: Numeric Format String
page_title: .NET MAUI NumericInput Documentation | Numeric String Format
description: Check our &quot;Numeric String Format&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 3
slug: numericinput-numeric-string-format
---

# Numeric Input Value Formatting

The NumericInput provides you the option to define the format of its numeric value. The desired format which will be applied when the control loses focus.

## String Format

The `StringFormat`(`string`) specifies the string format applied to the numeric value when the control loses focus.

## Standard Numeric Format Strings

You can find detailed information about the supported numeric formats in the [Standard Numeric Format Strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings) Microsoft documentation.

## Example

1. Define the NumericInput.

 ```XAML
<telerikInput:RadNumericInput x:Name="numericStrFormat" StringFormat="{}{0:C2}" />
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```


The following image shows the end result:

![NumericInput String Format](images/numericinput-string-format.png)

## See Also

- [Globalization]({%slug numericinput-globalization%})
- [Commands]({%slug numericinput-commands%})
