---
title: Picker Mode
page_title: .NET MAUI TimeSpanPicker Documentation - Picker Mode
description: Define PickerMode of Telerik TimeSpanPicker for .NET MAUI to either DropDown or Popup.
position: 5
slug: timespanpicker-picker-mode
---  

# .NET MAUI TimeSpanPicker Modes

The TimeSpanPicker for .NET MAUI provides a popup and a drop-down picker mode for picking a value from the selector.

## Picker Mode

Use the `PickerMode` (enum of type `Telerik.Maui.Controls.PickerMode`) property to specify which UI to open for selecting a value from the picker selector. The options are:

* `Popup`&mdash;Shows the UI for picking a time span inside a popup. It's the default value for mobile (Android and iOS);
* `DropDown`&mdash;Opens the UI for picking a time span inside a drop-down. It's the default value for Desktop (Windows, macOS);

Here is a sample of `PickerMode` set to `Popup`:

```XAML
<telerik:RadTimeSpanPicker Time="5:10:30:00"
                                PickerMode="Popup"/>
```

Check below the result on mobile and desktop:

![TimeSpanPicker Picker Mode](images/timespanpicker-pickermode-popup.png)

Quick example of `PickerMode` set to `DropDown`:

```XAML
<telerik:RadTimeSpanPicker Time="5:10:30:00"
                                PickerMode="DropDown"/>
```

Check the result of `DropDown` mode on mobile and desktop:

![TimeSpanPicker Picker Mode](images/timespanpicker-pickermode-dropdown.png)

## Picker Toggle State

You can control whether the picker popup or drop-down is opened or closed by using the `IsOpen`(`bool`) property.

## Toggle Button

In addition, TimeSpanPicker exposes `IsToggleButtonVisible` property which when set to `True` renders an "arrow" button for opening the UI for picking a time. By default, `IsToggleButtonVisible` is enabled for Desktop together with the `DropDown` picker mode, and is disabled for mobile platforms. You can explicitly apply it in both cases:

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
