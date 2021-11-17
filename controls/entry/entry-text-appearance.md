---
title: Text Appearance
page_title: .NET MAUI Entry Documentation | Text Appearance
description: "Use the text input configuration options of the Telerik UI for .NET MAUI Entry control and show a watermark, set the read-only state, define the max length of the input, and more."
position: 2
slug: entry-text-appearance
---

# Text Appearance

The Entry provides a number of settings for configuring the appearance of the text it displays such as the text input itself, adding a watermark to the text, setting the Entry in its read-only state, and so on.

## Setting the Text Input

The following properties are related to the Entry Text appearance and alignment:

* `Text`(`string`)&mdash;Defines the text.
* `TextColor`(`Color`)&mdash;Defines the color of the visible Entry text.
* `VerticalTextAlignment` (of type `Xamarin.Forms.TextAlignment`)&mdash;Specifies the vertical alignment of the text.
* `HorizontalTextAlignment` (of type `Xamarin.Forms.TextAlignment`)&mdash;Specifies the horizontal alignment of the text.
* `Padding`(`Thickness`)&mdash;Defines the padding of the text.

## Adding Watermarks

The Entry exposes the `WatermarkText`(`string`) property that prompts users what kind of information they  are expected to enter in the text input. The watermark text is displayed when the control is empty.  Additionally, you can set the `WatermarkTextColor`(`Color`) to customize the look of the watermark text as demonstrated in the following example.

```XAML
<telerikInput:RadEntry WatermarkText="First Name"
					   WatermarkTextColor="#6EA3FF" />
```

In the provided example:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

The following image shows the end result.

![Entry with Watermark](images/entry_watermark.png)

## Setting the Read-Only State

You can choose whether the Entry control is editable for end users or not by setting its read-only state through the `IsReadOnly` `bool` property. By default, `IsReadOnly` is set to `False`. To restrict the control from editing, set the `IsReadOnly` to `True`.

```XAML
<telerikInput:RadEntry x:Name="telerikEntry"
					   Text="Telerik UI for Xamarin Entry control"
					   IsReadOnly="True" />
```

## Defining the Max Length

You can restrict the number of the symbols the Entry control allows for its input field by using the `MaxLength` (`int`) property.

The following example demonstrates how to set the maximum length of the input to 10 symbols.

```XAML
<telerikInput:RadEntry x:Name="telerikEntry"
					   WatermarkText="Enter text"
					   MaxLength="10" />
```

## Setting the Keyboard Type

The `Keyboard` property of type `Xamarin.Forms.Keyboard` allows you to define the type of the keyboard that will be visualized by the device.

```XAML
<telerikInput:RadEntry x:Name="entry"
                       Keyboard="Numeric"
                       WatermarkText="Watermark Text" />
```

## See Also

- [Text Selection]({%slug entry-text-selection %})
- [Events]({% slug entry-events%})
- [Styling]({% slug entry-styling%})
