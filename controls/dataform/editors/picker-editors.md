---
title: Picker Editors
page_title: .NET MAUI DataForm Documentation | Picker Editors
description: "Check our &quot;Picker Editors&quot; documentation article for Telerik DataForm for .NET MAUI control."
position: 2
slug: dataform-picker-editors
---

# .NET MAUI DataForm Picker Editors

You can use the following Picker Editors the DataForm provides:

* `DataFormRadDatePickerEditor`&mdash;of type `RadDatePicker`({%slug datepicker-overview%})
* `DataFormRadDateTimePickerEditor` &mdash;of type `RadDateTimePicker`({%slug datetimepicker-overview%})
* `DataFormRadTimePickerEditor` &mdash;of type `RadTimePicker`({%slug timepicker-overview%})
* `DataFormRadTimeSpanPickerEditor` &mdash;of type `RadTimeSpanPicker`({%slug timespanpicker-overview%})

* `DataFormRadListPickerEditor` &mdash;of type `RadListPicker`({%slug listpicker-overview%})

* `DataFormDatePickerEditor` &mdash;of type `.NET MAUI DatePicker`
* `DataFormTimePickerEditor` &mdash;of type `.NET MAUI TimePicker`

Each Picker Editor has a Placeholder property.

## Styling 

You can easily style the editors using the properties BackgroundColor, BorderColor and BorderThickness. You can additionally style each editor by applying a style with the same target type as the underlying control.

A table with all editors and their control types is available in the [Editors Overview article]({%slug dataform-editors%}).

**Example with DataFormRadTextMaskedEditor**

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
For more information about how to style the editors, review the [Editors Styling article]({%slug dataform-editors-styling%}).