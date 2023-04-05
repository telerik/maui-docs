---
title: Modes and Buttons
page_title: .NET MAUI DatePicker Documentation - Picker Modes
description: "Define PickerMode of Telerik DatePicker for .NET MAUI to either DropDown or Popup."
position: 6
slug: datepicker-picker-mode
---

# .NET MAUI DatePicker Modes

The DatePicker for .NET MAUI provides a popup and a drop-down picker mode.

## Popup Picker Mode

To set the popup picker mode of the DatePicker, use the `PickerMode` property of the `Telerik.Maui.Controls.PickerMode` type and configure it to `Popup`. `Popup` shows the UI for picking a date inside a popup and is the default value for mobile (Android and iOS).

The following example shows how to set the `PickerMode` to `Popup`:

```XAML
<telerik:RadDatePicker Date="2020,05,15"
							DisplayStringFormat="yyy-ddd-MMM"
							PickerMode="Popup"  />
```

The image below shows the result on mobile and desktop devices:

![DatePicker Picker Mode](images/datepicker-pickermode-popup.png)

## Drop-Down Picker Mode

To set the drop-down picker mode of the DatePicker, use the `PickerMode` property of the `Telerik.Maui.Controls.PickerMode` type and configure it to `DropDown`. The `DropDown` value opens the UI for picking a date inside a drop-down, and is the default value for Desktop (Windows, macOS).

The following example shows how to set the `PickerMode` to `DropDown`:

```XAML
<telerik:RadDatePicker Date="2020,05,15"
							DisplayStringFormat="yyy-ddd-MMM"
							PickerMode="DropDown"  />
```

The image below shows the result on mobile and desktop devices:

![DatePicker Picker Mode](images/datepicker-pickermode-dropdown.png)

## Arrow Picker Mode

In addition, DatePicker exposes the `IsToggleButtonVisible` property which, when set to `True`, renders an `Arrow` button for opening the UI and allows users to pick a date.

By default, together with the `DropDown` picker mode, `IsToggleButtonVisible` is enabled for desktop devices, and is disabled for mobile platforms. Still, you can explicitly apply it in both cases by using the following implementation:

```XAML
<telerik:RadDatePicker Date="2020,05,15"
							DisplayStringFormat="yyy-ddd-MMM"
							PickerMode="DropDown"
							IsToggleButtonVisible="True" />
```

## See Also

- [Formatting the Telerik UI for .NET MAUI DatePicker]({%slug datepicker-formatting%})
- [Setting Date Ranges in the .NET MAUI DatePicker]({%slug datepicker-date-range%})
- [.NET MAUI DatePicker Templates]({%slug datepicker-templates%})
- [.NET MAUI DatePicker Selection]({%slug datepicker-selection%})
- [.NET MAUI DatePicker Styling]({%slug datepicker-styling%})
- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
