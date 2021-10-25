---
title: Formatting
page_title: .NET MAUI TimeSpan Picker Documentation | TimeSpan Format Strings
description: Check our &quot;Formatting&quot; documentation article for Telerik TimeSpan Picker for .NET MAUI.
position: 2
slug: timespan-picker-formatting
---


# TimeSpan Formatting

Time Picker for .NET MAUI allows you to use standard or custom time format strings. Set formatting to the spinners that are displayed when the picker is opened - through the `SpinnerFormat` property and when time is selected through the `DisplayStringFormat` property. 

## DisplayString Format

* `DisplayStringFormat`(*string*): Defines the format of the string that will be visualized when the picker dialog is closed. 

>note The format set for **DisplayStringFormat** should be a valid time span format - [Standard Time Formst Strings]({%slug timespan-picker-formatting%}#standard-timespan-format-strings) and [Custom Time format Strings]({%slug timespan-picker-formatting%}#custom-timespan-format-strings). 

## Spinner Format

TimeSpan Picker for Xamarin allows you to use standard or custom timespan format strings through the `SpinnerFormat` property. Depending on what format is set, the picker visualizes spinner controls with prepopulated values to be picked.

* `SpinnerFormat`(*string*): Defines the string format for the spinners. The default format is **"g"**.

## Standard TimeSpan Format Strings

The available Standard TimeSpan Format Strings which can be set to the SpinnerFormat property are described in the table below:

| Supported Standard TimeSpan Format String | Description |
| -------- | -------- |
| "G" | General Long "G" format specifier |
| "g" | General Short "g" format specifier |
| "c" | Constant "c" format specifier |

>important You can set only short [Standard TimeSpan Format Strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-timespan-format-strings) to the TimeSpan Picker control.

## Custom TimeSpan Format Strings

The available Custom TimeSpan Format Strings which can be set to the SpiinerFormat property are described in the table below:

| Supported Custom TimeSpan Format Strings|
| -------- |
| "d" |
| "dd" |
| "ddd" |
| "dddd" |
| "h" |
| "hh" |
| "m" |
| "mm" |
| "s" |
| "ss" |


>important You can set only short [Custom TimeSpan Format Strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-timespan-format-strings) to the TimeSpan Picker control.

## Supported Separators

When SpinnerFormat is set and device culture is changed, the separators used for the format string won't be changed:

| Supported Separator Formats |
| -------- |
| "-" |
| "." |
| "," |
| " " |
| ":" |
| "/" |

## See Also

- [Templates]({%slug timespan-picker-templates%})
- [Styling]({%slug timespan-picker-styling%})
- [Selection]({%slug timespan-picker-selection%})
- [Commands]({%slug timespan-picker-commands%})
