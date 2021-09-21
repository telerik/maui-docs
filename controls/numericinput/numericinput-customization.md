---
title: Customization
page_title: .NET MAUI NumericInput Documentation | Customization
description: Check our &quot;Customization&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 5
slug: numericinput-customization
---

# Customization Options

This article will guide you through all customizations options that NumericInput control provides.

## Numeric Input Buttons Text

![NumericInput Button Text Default Look](images/numericinput-getting-started.png "NumericInput Button Text Default Look")

* `IncreaseButtonText`(of type string): Defines the text displayed inside the IncreaseButton. The default string calue is "+".
* `DecreaseButtonText`(of type string): Defines the text displayed inside the DecreaseButton. The default string calue is "-".

## Customze Buttons Text

![NumericInput Button Text Customization](images/numericinput-buttons-customization.png "NumericInput Button Text Customization")

```XAML
 <telerikInput:RadNumericInput x:Name="numericBtnText" IncreaseButtonText="&gt;" DecreaseButtonText="&lt;" />
```

Add the following namespase: 

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## Change BackgroundColor 

* **BackgroundColor**: allows you to change the background color of the NumericInput control.

## See Also

- [Globalization]({%slug numericinput-globalization%})
- [Commands]({%slug numericinput-commands%})
