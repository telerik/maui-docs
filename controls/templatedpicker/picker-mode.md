---
title: Picker Mode
page_title: .NET MAUI TemplatedPicker Documentation - Picker Mode
description: "Define PickerMode of Telerik TemplatedPicker for .NET MAUI to either DropDown or Popup."
position: 5
slug: templatedpicker-picker-mode
---  

# .NET MAUI TemplatedPicker Modes

The TemplatedPicker for .NET MAUI exposes `PickerMode` property of `Telerik.Maui.Controls.PickerMode` type which can be set to one of the following values:

* `Popup`&mdash;Shows the UI for picking a date inside a popup. It's the default value for mobile (Android and iOS);
* `DropDown`&mdash;Opens the UI for picking a date inside a dropdown. It's the default value for Desktop (Windows, macOS);

Here is a sample of `PickerMode` set to `Popup`:

```XAML
<telerik:RadTemplatedPicker PickerMode="Popup" />
```

Check below the result on mobile and desktop:

![CustomPicker Picker Mode](images/templatedpicker-pickermode-popup.png)

Quick example of `PickerMode` set to `DropDown`:

```XAML
<telerik:RadTemplatedPicker PickerMode="DropDown" />
```

Check the result of `DropDown` mode on mobile and desktop:

![.NET MAUI TemplatedPicker Drop-down mode](images/templatedpicker-pickermode-dropdown.png)

> Go to [Getting Started]({%slug templatedpicker-getting-started%}) topic for the complete example with the TemplatedPicker control.

## Toggle Button

In addition, TemplatedPicker exposes `IsToggleButtonVisible` property which when set to `True` renders an "arrow" button for opening the UI for picking a time. By default, `IsToggleButtonVisible` is enabled for Desktop and disabled for mobile platforms. Still, you can explicitly apply it in both cases:

```XAML
<telerik:RadTemplatedPicker PickerMode="DropDown"
							IsToggleButtonVisible="True" />
```

## See Also

- [Templates]({%slug templatedpicker-templates%})
- [Styling]({%slug templatedpicker-styling%})
- [Commands]({%slug templatedpicker-commands%})
