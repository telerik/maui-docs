---
title: Setting the Keyboard
page_title: .NET MAUI MaskedEntry Documentation - Setting the Keyboard
description: Learn how to set the Keyboard type in Telerik UI for .NET MAUI MaskedEntry.
position: 12
slug: maskedentry-keyboard
---

# .NET MAUI MaskedEntry - Keyboard Type

You can change the keyboard type of the MaskedEntry by setting the `Keyboard`(of type `Microsoft.Maui.Keyboard`) property. The available options are: `Plain`, `Chat`, `Default`, `Email`, `Numeric`, `Telephone`, `Text`, `Uri`.

Example with setting the `Keyboard` to `Numeric` on `TextMaskedEntry`

```XAML
<telerik:RadTextMaskedEntry x:Name="maskedEntry"
                            Keyboard="Numeric"
                            Mask="00:00" />
```

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Events]({%slug maskedentry-events%})
- [Styling]({%slug maskedentry-styling%})
