---
title: Picker Mode
page_title: .NET MAUI TimeSpanPicker Documentation | Picker Mode
description: "Define PickerMode of Telerik TimeSpanPicker for .NET MAUI to either DropDown or Popup."
position: 5
slug: timespanpicker-picker-mode
---  

# Picker Mode

The TimeSpanPicker for .NET MAUI exposes `PickerMode` property of `Telerik.XamarinForms.Input.PickerMode` type which can be set to one of the following values:

* `Popup`&mdash;Shows the UI for picking a date inside a popup. It's the default value for mobile (Android and iOS);
* `DropDown`&mdash; Opens the UI for picking a date inside a dropdown. It's the default value for Desktop (Windows, macOS);

Here is a sample of `PickerMode` set to `Popup`:

```XAML
<telerik:RadTimeSpanPicker Time="5:10:30:00"
                                PickerMode="Popup"/>
```

Check below the result on mobile and desktop:

![](images/timespanpicker-pickermode-popup.png)

Quick example of `PickerMode` set to `DropDown`:

```XAML
<telerik:RadTimeSpanPicker Time="5:10:30:00"
                                PickerMode="DropDown"/>
```

Check the result of `DropDown` mode on mobile and desktop:

![](images/timespanpicker-pickermode-dropdown.png)

## Toggle Button

In addition, TimeSpanPicker exposes `IsToggleButtonVisible` property which when set to `True` renders an "arrow" button for opening the UI for picking a time. By default, `IsToggleButtonVisible` is enabled for Desktop together with the `DropDown` picker mode, and is disabled for mobile platforms. Still, you can explicitly apply it in both cases:

```XAML
<telerik:RadTimeSpanPicker Time="5:10:30:00"
								PickerMode="DropDown"
								IsToggleButtonVisible="True" />
```

## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Styling]({%slug timespanpicker-styling%})
- [Commands]({%slug timespanpicker-commands%})
- [Selection]({%slug timespanpicker-selection%})
