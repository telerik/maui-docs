---
title: Localization
page_title: .NET MAUI DateTimePicker Documentation | Localization
description: "Use the localization options of the DateTimePicker for .NET MAUI."
position: 4
slug: datetimepicker-localization
---

# Date and Time Picker Localization

Telerik UI for .NET MAUI DateTimePicker provides language localization. In short, you can translate the used across the Date and Time Picker texts to other languages, so that your app can be adapted to different regions.

>important To learn in details about the localization process of Telerik UI for Xamarin components, please go through the common [Localization and Globalization]({%slug globalization-localization%}) topic.

The sections below list all the localization keys used in Date and Time Picker Spinners.

## Date and Time Spinners Localization Keys

| Localization Key | Default Value |
| -----------------| ------------- |
| DateTimePicker_Popup_HeaderLabelText  | Select Date and Time |
| DateTimePicker_PlaceholderLabelText  | Select Date and Time |

## Common Picker Localizations strings

| Localization Key | Default Value |
| -----------------| ------------- |
| Picker_AmPmSpinnerHeaderLabelText  | AM/PM |
| Picker_DaySpinnerHeaderLabelText  | Day |
| Picker_HourSpinnerHeaderLabelText  | Hours |
| Picker_MinuteSpinnerHeaderLabelText | Minutes |
| Picker_SecondSpinnerHeaderLabelText  | Seconds |
| Picker_MonthSpinnerHeaderLabelText  | Month |
| Picker_YearSpinnerHeaderLabelText  | Year |
| Picker_Popup_AcceptButtonText  | OK |
| Picker_Popup_CancelButtonText  | Cancel |

Check in the image below how the localization strings are presented in Date and Time Picker:

![DateTime Picker Localization](images/datetimepicker-localization.png)

## Example with CustomLocalizationManager

The snippet below shows a simple RadDateTimePicker definition:

<snippet id='datetime-picker-localization-xaml' />

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

Create a custom class that inherits from TelerikLocalizationManager and override the GetString() method:

<snippet id='datetimepicker-localization-code-behind' />

Set it as the TelerikLocalizationManager.Manager:

>important A sample Localization example can be found in the DateTimePicker/Features folder of the [SDKBrowser Demo application]({%slug maui-demo-app%}).

## See Also

* [Localization and Globalization]({%slug globalization-localization%})
