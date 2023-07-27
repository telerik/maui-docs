---
title: Formatting
page_title: .NET MAUI TimeSpanPicker Documentation - TimeSpan Format Strings
description: Learn more about the time formatting that the Telerik UI for .NET MAUI TimeSpanPicker provides.
position: 2
previous_url: /controls/timespanpicker/timespanpicker-formatting
slug: timespanpicker-formatting
---

# .NET MAUI Time Span Formatting

The TimeSpanPicker for .NET MAUI allows you to use standard or custom time format strings.

To set formatting to the spinners that are displayed when the picker is opened, use the `SpinnerFormat` property. To set formatting to the spinners that are displayed when time is selected, use the `DisplayStringFormat` property.

## Display String Format

To define the format of the string that will be visualized when the picker dialog is closed, use the `DisplayStringFormat`(`string`) property.

>note The format set for `DisplayStringFormat` has to be a valid time span format. For more information, refer to the [Standard Time Format Strings]({%slug timepicker-formatting%}#standard-time-format-strings) and [Custom Time Format Strings]({%slug timepicker-formatting%}#custom-time-format-strings) articles.

## Spinner Format

The TimeSpanPicker allows you to use standard or custom time span format strings through the `SpinnerFormat` property. Depending on what format is set, the picker visualizes spinner controls with -prepopulated values that can be picked.

To define the string format for the spinners, use the `SpinnerFormat`(`string`) property. The default format is `"g"`.

## Standard Time Span Format Strings

The available standard time-span format strings that can be set to the `SpinnerFormat` and `DisplayStringFormat` properties are described in the table below:

| Supported Standard TimeSpan Format String | Description |
| -------- | -------- |
| `"G"` | General Long "G" format specifier |
| `"g"` | General Short "g" format specifier |
| `"c"` | Constant "c" format specifier |

>important You can set only short [Standard Time Span Format Strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-timespan-format-strings) to the TimeSpanPicker control.

## Custom Time Span Format Strings

The available custom time span format strings that can be set to the `SpinnerFormat` and `DisplayStringFormat` properties are described in the table below:

The Supported Custom Time Span Format Strings are: `"d"`, `"dd"`, `"ddd"`, `"dddd"`, `"h"`, `"hh"`, `"m"`, `"mm"`, `"s"`, `"ss"`.

**Example for custom time span formatting for d:hh:mm**

```XAML
<telerik:RadTimeSpanPicker DefaultHighlightedTime="5:10:30:00"
                           SpinnerFormat="d\:hh\:mm"
                           DisplayStringFormat="d\:hh\:mm"/>
```

>important You can set only short [Custom Time Span Format Strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-timespan-format-strings) to the TimeSpanPicker control.

## Supported Separators

When the `SpinnerFormat` is set and the device culture is changed, the separators used for the format string won't be updated.

The following table lists the available separators:

The Supported Time Span Format Separators are: `"-"`, `"."`, `","`, `" "`, `":"`,`"/"`.

## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Styling]({%slug timespanpicker-styling%})
- [Selection]({%slug timespanpicker-selection%})
- [Commands]({%slug timespanpicker-commands%})
