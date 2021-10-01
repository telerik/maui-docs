---
title: Text Appearance
page_title: .NET MAUI Entry Documentation | Text Appearance
description: Check our &quot;Text Appearance&quot; documentation article for Telerik Entry for .NET MAUI control.
position: 2
slug: entry-text-appearance
---

# Text Appearance

The purpose of this help article is to show you the key features of the **RadEntry** control related to text appearance. 

## Text

The following properties are related to the Entry Text appearance and alignment:

* **Text**(*string*): Defines the Text;
* **TextColor**(*Color*): Defines the color of the visible text of the RadEntry control.
* **VerticalTextAlignment**(*of type Xamarin.Forms.TextAlignment*): Specifies the vertical alignment of the RadEntry.Text;
* **HorizontalTextAlignment**(*of type Xamarin.Forms.TextAlignment*): Specifies the horizontal alignment of the RadEntry.Text;
* **Padding**(*Thickness*): Defines the Padding of the text;

## Watermark 

RadEntry exposes **WatermarkText**(*string*) property used to give guidance to the end user on what should be entered in the text input. The watermark text is displayed when the control is empty.  Additionally, you could set **WatermarkTextColor**(*Color*) to customize the look of the watermark text. 

```XAML
<telerikInput:RadEntry WatermarkText="First Name" 
					   WatermarkTextColor="#6EA3FF" />
```

Where:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

![Entry with Watermark](images/entry_watermark.png)

## Read-Only State

RadEntry control provides a feature which allows you to choose whether the control will be editable or not - Read-Only state.

* **IsReadOnly** *bool* property: Specifies whether the control will be in edit mode. The default value is `False`. If you want to restrict the control from editing, set the `IsReadOnly` to `True`

```XAML
<telerikInput:RadEntry x:Name="telerikEntry" 
					   Text="Telerik UI for Xamarin Entry control" 
					   IsReadOnly="True" />
```

## Max Length

With RadEntry you can restrict the number of the symbols allowed to be entered in the input field. 

* **MaxLength** (*int*) property: Specifies the maximum number of symbols allowed to be entered.

### Example with MaxLength set to 10

```XAML
<telerikInput:RadEntry x:Name="telerikEntry" 
					   WatermarkText="Enter text" 
					   MaxLength="10" />
```

## Keyboard

The **Keyboard** property of type *Xamarin.Forms.Keyboard* allows you to define the type of the keyboard that will be visualized by the device.

```XAML
<telerikInput:RadEntry x:Name="entry" 
                       Keyboard="Numeric"
                       WatermarkText="Watermark Text" />
```

## See Also

- [Text Selection]({%slug entry-text-selection %})
- [Events]({% slug entry-events%})
- [Styling]({% slug entry-styling%})
