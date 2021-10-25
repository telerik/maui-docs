---
title: Formatting
page_title: .NET MAUI Time Picker Documentation | Time Format Strings
description: Check our &quot;Time Format Strings&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 2
slug: time-picker-formatting
---

# Time Formatting

Time Picker for .NET MAUI allows you to use standard or custom time format strings. Set formatting to the spinners that are displayed when the picker is opened - through the `SpinnerFormat` property and when time is selected through the `DisplayStringFormat` property. 

## DisplayString Format

* `DisplayStringFormat`(*string*): Defines the format of the string that will be visualized when the picker dialog is closed. 

>note The format set for **DisplayStringFormat** should be a valid time format - [Standard Time Formst Strings]({%slug time-picker-formatting%}#standard-time-format-strings) and [Custom Time format Strings]({%slug time-picker-formatting%}#custom-time-format-strings). 

### Example 

```XAML
<telerikInput:RadTimePicker DisplayStringFormat="H:mm"/>
```

and namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## Spinner Format

* `SpinnerFormat`(*string*): Defines the string format for the spinners. The default format is **"g"**. Depending on what format is set, the picker visualizes spinner controls with prepopulated values to be picked.

## Standard Тime Format Strings

The available standard date and time format strings that can be set to the SpinnerFormat property are described in the table below:

| Supported Standard Time Format String | Description |
| -------- | -------- |
| "G" | Short Date and Long Time Format Specifier |
| "g" | Short Date and Short Time Format Specifier |
| "T" | Long Time Format Specifier |
| "t" | Short Time Format Specifier |

>tip For more information on different format go to [Standard Date and Time Format Strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-date-and-time-format-strings) topic on Microsoft Docs.

## Custom Time Format String

The available custom time format strings that can be set to the SpinnerFormat property are described in the table below:

| Supported Custom Time Format Strings|
| -------- |
| "H" |
| "HH" |
| "h" |
| "hh" |
| "m" |
| "mm" |
| "s" |
| "ss" |
| "t" |
| "tt" |
 
>tip For more details on different formats go to [Custom Date and Time Format Strings](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings) topic on Microsoft Docs.

## Supported Separators

When SpinnerFormat is set and device culture is changed, the separators used for the format string won't be changed. Check below a list of the available separators:

| Supported Time Separators Formats |
| -------- |
| "-" |
| "." |
| "'" |
| " " |
| ":" |
| "/" |

## Example

### SpinnerFormat="H:mm"

```XAML
<telerikInput:RadTimePicker SpinnerFormat="H:mm" />
```

And the result:

![](images/timepicker-string-format-H-mm.png)

## See Also

- [Templates]({%slug time-picker-templates%})
- [Styling]({%slug time-picker-styling%})
- [Commands]({%slug time-picker-commands%})
