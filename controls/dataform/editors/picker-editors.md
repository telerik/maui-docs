---
title: Picker Editors
page_title: .NET MAUI DataForm Documentation - Picker Editors
description: Learn more about the pickers editors that Telerik UI for .NET MAUI provides.
position: 2
slug: dataform-picker-editors
---

# .NET MAUI DataForm Picker Editors

This article explains all picker editors available in Telerik .NET MAUI DataForm control.

## Picker Editors Based on Telerik .NET MAUI Controls:

* `DataFormRadDatePickerEditor`&mdash;Of type [`RadDatePicker`]({%slug datepicker-overview%})
* `DataFormRadDateTimePickerEditor`&mdash;Of type [`RadDateTimePicker`]({%slug datetimepicker-overview%})

Shared properties for `DataFormRadDatePickerEditor` and `DataFormRadDateTimePickerEditor` are:

* `MinimumDate`(`DateTime?`)&mdash;Specifies the minimum date for the editor.
* `MaximumDate`(`DateTime?`)&mdash;Specifies the maximum date for the editor.
* `FallbackDate`(`DateTime?`)&mdash;Specifies the fallback date for the editor.

* `DataFormRadTimePickerEditor`&mdash;Of type [`RadTimePicker`]({%slug timepicker-overview%})
* `DataFormRadTimeSpanPickerEditor`&mdash;Of type [`RadTimeSpanPicker`]({%slug timespanpicker-overview%})

Shared properties for `DataFormRadTimePickerEditor` and `DataFormRadTimeSpanPickerEditor` are:

* `MinimumDate`(`DateTime?`)&mdash;Specifies the minimum time for the editor.
* `MaximumDate`(`DateTime?`)&mdash;Specifies the maximum time for the editor.
* `FallbackDate`(`DateTime?`)&mdash;Specifies the fallback time for the editor.
* `HoursStep`(`int?`)&mdash;Specifies the hours step for the editor.
* `MinutesStep`(`int?`)&mdash;Specifies the minutes step for the editor.
* `SecondsStep`(`int?`)&mdash;Specifies the seconds step for the editor.

* `DataFormRadListPickerEditor`&mdash;Of type [`RadListPicker`]({%slug listpicker-overview%}). The editor has an `ItemsSource` property that specifies a collection of items to use with the `RadListPicker`. When no items are specified and the picker is bound to a property of type enum, the items are populated automatically from the available enum values. 


## Picker editors based on .NET MAUI controls:

* `DataFormDatePickerEditor`&mdash;Of type `.NET MAUI DatePicker`
* `DataFormTimePickerEditor`&mdash;Of type `.NET MAUI TimePicker`


Other properties that are common for all editors are listed in the [Editors Overview]({%slug dataform-editors%}#common-properties) article.


## Common properties

* By using the `Placeholder` property (`string`) you can provide hints or examples that show the users what information to enter.

You can style the editors using the properties `BackgroundColor`, `BorderColor` and `BorderThickness`. You can additionally style each editor by applying a style with the same target type as the underlying control.

A table with all editors and their control types is available in the [Editors Overview article]({%slug dataform-editors%}).

>note More information about how to style the editors, review the [Editors Styling article]({%slug dataform-editors-styling%}).

Example with `DataFormRadTextMaskedEditor`

```XAML
<Style x:Key="RadDatePickerStyle" TargetType="telerik:RadDatePicker">
    <Setter Property="Placeholder"
            Value="Enter the starting date" />
    <Setter Property="MinimumDate"
            Value="2022,1,1" />
    <Setter Property="IsToggleButtonVisible"
            Value="False" />
</Style>
```

And the editor definition

```XAML
<telerik:DataFormRadDatePickerEditor PropertyName="StartDate"
                                     HeaderText="Start Date"
                                     BackgroundColor="LightSteelBlue"
                                     BorderColor="DarkGray"
                                     BorderThickness="2"
                                     EditorStyle="{StaticResource RadDatePickerStyle}"/>
```

## See Also

- [Editors]({%slug dataform-editors%})