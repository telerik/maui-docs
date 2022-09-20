---
title: Boolean Editors
page_title: .NET MAUI DataForm Documentation | Boolean Editors
description: "Check our &quot;Boolean Editors&quot; documentation article for Telerik DataForm for .NET MAUI control."
position: 3
slug: dataform-boolean-editors
---

# .NET MAUI DataForm Boolean Editors

You can use the following Boolean Editors the DataForm provides:

* `DataFormRadCheckBoxEditor` &mdash;of type `RadCheckBox`({%slug checkbox-overview%})
* `DataFormSwitchEditor`&mdash;of type `.NET MAUI Switch`


## Styling 

You can easily style the editors using the properties BackgroundColor, BorderColor and BorderThickness. You can additionally style each editor by applying a style with the same target type as the underlying control.

A table with all editors and their control types is available in the [Editors Overview article]({%slug dataform-editors%}).

**Example with DataFormRadTextMaskedEditor**

```XAML
<Style x:Key="RadDateBooleanStyle" TargetType="telerik:RadDateBoolean">
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
<telerik:DataFormRadDateBooleanEditor PropertyName="StartDate"
                                     HeaderText="Start Date"
                                     BackgroundColor="LightSteelBlue"
                                     BorderColor="DarkGray"
                                     BorderThickness="2"
                                     EditorStyle="{StaticResource RadDateBooleanStyle}"/>
```
For more information about how to style the editors, review the [Editors Styling article]({%slug dataform-editors-styling%}).