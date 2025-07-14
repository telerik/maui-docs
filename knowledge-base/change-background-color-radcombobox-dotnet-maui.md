---
title: Changing Background Color of RadComboBox Based on Selected Item
description: Learn how to change the background color of the RadComboBox for .NET MAUI depending on the selected item.
type: how-to
page_title: Change Background Color of RadComboBox Items in .NET MAUI
meta_title: Change Background Color of RadComboBox Items Based on Selection in .NET MAUI
slug: change-background-color-radcombobox-dotnet-maui
tags: combobox,.net maui,background color,selectionboxtemplate
res_type: kb
ticketid: 1692680
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.1 | Telerik UI for .NET MAUI ComboBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to change the background color of the entire [ComboBox](https://docs.telerik.com/devtools/maui/controls/combobox/overview) control based on the selected item. The text always appears with a white background, and I need to apply a specific background color to the entire control.

This knowledge base article also answers the following questions:
- How to apply different background colors to ComboBox items in .NET MAUI?
- How to use `SelectionBoxTemplate` to customize `RadComboBox` background?
- How to make the `RadComboBox` reflect selected item background color?

## Solution

To change the background color of the `RadComboBox` based on the selected item, use the `SelectionBoxTemplate` property, which is available when the control is non-editable (`IsEditable` set to `False`). The `SelectionBoxTemplate` allows you to customize the appearance of the selected item.

1. Set the `IsEditable` property to `False`.
2. Define a `SelectionBoxTemplate` with a `DataTemplate` to specify the background color of the selected item.
3. Use the `SelectedItemTemplate` and `ItemTemplate` to provide consistent styling for all items.

Here is an example:

```xaml
<VerticalStackLayout>
    <telerik:RadComboBox ItemsSource="{Binding Items}" 
                         DisplayMemberPath="Name" 
                         IsEditable="False"
                         Placeholder="Select City">
        <telerik:RadComboBox.ItemTemplate>
            <DataTemplate>
                <telerik:RadBorder BackgroundColor="LightYellow"
                                   MinimumWidthRequest="300">
                    <Label Text="{Binding Name}" 
                           Padding="8, 7, 0, 7"
                           TextColor="Black"/>
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
        <telerik:RadComboBox.SelectionBoxTemplate>
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
        </telerik:RadComboBox.SelectionBoxTemplate>
    </telerik:RadComboBox>
</VerticalStackLayout>
```

- The `ItemTemplate` sets the background color for the items in the dropdown list.
- The `SelectedItemTemplate` specifies the appearance of the selected item in the dropdown list.
- The `SelectionBoxTemplate` applies the background color to the non-editable view of the selected item, ensuring consistency.

## See Also

- [ComboBox Overview](https://docs.telerik.com/devtools/maui/controls/combobox/overview)
- [ComboBox Templates](https://docs.telerik.com/devtools/maui/controls/combobox/templates)
