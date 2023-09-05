---
title: Commands
page_title: .NET MAUI NumericInput Documentation - Commands
description: Learn how to use the exposed commands in the Telerik UI for .NET MAUI NumericInput control.
position: 9
previous_url: /controls/numericinput/numericinput-commands
slug: numericinput-commands
---

# .NET MAUI NumericInput Commands

The NumericInput exposes `IncreaseCommand` and `DecreaseCommand` which can be used to define custom functionality upon the respective actions. These commands allow you to change and extend the control's default behavior.

In the next example, you can see how the NumericInput commands can be utilized to implement auto-reverse functionality – start from the Minimum value when the Maximum is reached and vice versa.

**1.** First, create the `ViewModel` with both `IncreaseCommand` and `DecreaseCommand` implementations:

<snippet id='numericinput-features-commands-viewmodel' />

**2.** Define the NumericInput with the respective bindings:

 <snippet id='numericinput-features-commands' />

> For the NumericInput Commands example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to NumericInput -> Features category.


## See Also

- [Events]({%slug numericinput-events%})
