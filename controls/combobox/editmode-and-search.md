---
title: Edit Mode & Search
page_title: .NET MAUI ComboBox Documentation - Edit Mode & Search
description: Check our &quot;Edit Mode &amp; Search&quot; documentation article for Telerik UI for .NET MAUI ComboBox.
position: 4
slug: combobox-editmode-and-search
---

# .NET MAUI ComboBox Edit Mode & Search

ComboBox supports both **editable** and **noneditable** state. When the control is in edit mode, users can type into the input field and searching through the control's ItemsSource can be performed. 

This topic describes in details the configuration options related to the editable state of the ComboBox as well as its searching capabilities.

## Edit Mode

* `IsEditable`(`bool`): Defines whether typing into the input area can be performed. The default value is `false`.
* `SearchTextPath`(`string`): Defines the name of the property against which the searching will be performed. The property is usable when the control is in edit mode (`IsEditable` is `true`). 
* `OpenOnFocus`(`bool`): Specifies whether the dropdown will be shown as soon as the control is focused. The property is usable when the control is in edit mode (`IsEditable` is `true`).  The default value is `true`. If the property is set to false when the control is focused the drop-down will no longer open.
* `Text`(`string`): Specifies the Text of the control. This is the Text that gets visualized when the control is editable or when it is non-editable and the selection mode is single.

## Search

ComboBox provides both case-sensitive and case-insensitive searching modes. The following properties are exposed:

- `SearchMode` (enumeration of type *Telerik.Maui.Controls.SearchMode*): Defines the value that sets search sets some search criteria for the control. The available options are: `Contains`, `StartsWith`, `ContainsCaseSensitive` and `StartsWithCaseSensitive`. The default SearchMode is `StartsWith`.
- `SearchTexhPath`(`string`): Specifies the name of the property against which the searching will be performed.
* `HighlightTextColor` (*Microsoft.Maui.Graphics.Color*): Defines the color of the text that will be highlighted when searching is performed.

> Searching can be performed when `IsEditable` is set to `true`.

> When we want to set the HighlightTextColor property using custom templates, we have to use the `RadHighlightLabel class` inside the template.

Here is the example in XAML:

```XAML
<telerik:RadComboBox x:Name="comboBox"
        ItemsSource="{Binding Items}" 
        DisplayMemberPath="Name"
        Placeholder="Select City"
        AutomationId="comboBox"
        HighlightTextColor="Red"
        IsEditable="True">
    <telerik:RadComboBox.ItemTemplate>
        <DataTemplate>
            <telerik:RadBorder BackgroundColor="LightYellow"
                MinimumWidthRequest="300">

                <telerik:RadHighlightLabel TextColor="Black" Padding="10"
            HighlightTextColor="BlueViolet"
            UnformattedText="{Binding Name}"
            HighlightText="{Binding Source={x:Reference comboBox}, Path=Text}" />

            </telerik:RadBorder>
        </DataTemplate>
    </telerik:RadComboBox.ItemTemplate>
    <telerik:RadComboBox.SelectedItemTemplate>
        <DataTemplate>
            <telerik:RadBorder BackgroundColor="LightBlue"
                MinimumWidthRequest="300">
                <VerticalStackLayout>
                    <Label Text="{Binding Name}"
            Padding="8, 7, 0, 7"
            TextColor="Black"/>
                    <Label Text="{Binding Population}" 
            FontSize="12"
            Padding="8, 7, 0, 7"/>
                </VerticalStackLayout>
            </telerik:RadBorder>
        </DataTemplate>
    </telerik:RadComboBox.SelectedItemTemplate>
</telerik:RadComboBox>
 ```


## Example

Here is the ComboBox definition in XAML:

<snippet id='combobox-editing'/>

>note When binding to a complex objects, ComboBox `DisplayMemberPath` property should be set. Also when `IsEditable` is `true` `SearchTextPath` property should be set.

In addition to this, you need to add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

the sample business model

<snippet id='combobox-city-businessmodel'/>

and the ViewModel used:

<snippet id='combobox-cities-viewmodel'/>

Here is how the control looks in edit mode:

![ComboBox Edit Mode](images/combobox-edit.png)

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Single and Multiple Selection]({%slug combobox-selection%})
- [Templates]({%slug combobox-templates%})
