---
title: Picker Mode
page_title: .NET MAUI TemplatedPicker Documentation - Picker Mode
description: Learn how to set the PickerMode of the Telerik UI for .NET MAUI TemplatedPicker to either DropDown or Popup.
position: 5
slug: templatedpicker-picker-mode
---  

# .NET MAUI TemplatedPicker Modes

The TemplatedPicker for .NET MAUI provides a popup and a drop-down picker mode for picking a value from the selector.

## Picker Mode

Use the `PickerMode` (enum of type `Telerik.Maui.Controls.PickerMode`) property to specify which UI to open for selecting a value from the picker selector. The options are:

* `Popup`&mdash;Shows the UI for picking a value inside a popup. It's the default value for mobile (Android and iOS);
* `DropDown`&mdash;Opens the UI for picking a value inside a drop-down. It's the default value for Desktop (Windows, macOS);

Here is a sample of `PickerMode` set to `Popup`:

```XAML
<telerik:RadTemplatedPicker PickerMode="Popup" />
```

Check below the result on mobile and desktop:

![Custom Picker Picker Mode](images/templatedpicker-pickermode-popup.png)

Quick example of `PickerMode` set to `DropDown`:

```XAML
<telerik:RadTemplatedPicker PickerMode="DropDown" />
```

Check the result of `DropDown` mode on mobile and desktop:

![.NET MAUI TemplatedPicker Drop-down mode](images/templatedpicker-pickermode-dropdown.png)

> Go to [Getting Started]({%slug templatedpicker-getting-started%}) topic for the complete example with the TemplatedPicker control.

## Picker Toggle State

You can control whether the picker popup or drop-down is opened or closed by using the `IsOpen` (`bool`) property.

## Arrow Button Picker Mode

In addition, TemplatedPicker exposes `IsToggleButtonVisible` property which when set to `True` renders an "arrow" button for opening the UI for picking a time. By default, `IsToggleButtonVisible` is enabled for Desktop and disabled for mobile platforms. You can explicitly apply it in both cases:

```XAML
<telerik:RadTemplatedPicker PickerMode="DropDown"
							IsToggleButtonVisible="True" />
```

## See Also

- [Templates]({%slug templatedpicker-templates%})
- [Styling]({%slug templatedpicker-styling%})
- [Commands]({%slug templatedpicker-commands%})
