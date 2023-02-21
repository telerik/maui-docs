---
title: Setting the Keyboard
page_title: .NET MAUI MaskedEntry Documentation - Setting the Keyboard
description: "Learn how to set the Keyboard type in Telerik UI for .NET MAUI MaskedEntry."
position: 12
slug: maskedentry-keyboard
---

# Setting the Keyboard Type in .NET MAUI MaskedEntry

The `Keyboard` property allows you to define the type of the keyboard that will be visualized by the device.

### Keyboard Type for TextMaskEntry

```XAML
<telerik:RadTextMaskedEntry x:Name="maskedEntry"
                            Keyboard="Numeric"
                            Mask="00:00" />
```

### Keyboard Type for NumericMaskEntry

```XAML
<telerik:RadNumericMaskedEntry x:Name="maskedEntry"
                               Keyboard="Numeric"
                               Mask="C" />
```

### Keyboard Type for IPMaskedEntry

```XAML
<telerik: RadIPMaskedEntry x:Name="ipMaskedEntry"
                            Keyboard="Numeric"/>
```

### Keyboard Type for EmailMaskedEntry

```XAML
<telerik:RadEmailMaskedEntry x:Name="emailMaskedEntry1"
                             Keyboard="Numeric"/>
```


## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Events]({%slug maskedentry-events%})
- [Styling]({%slug maskedentry-styling%})