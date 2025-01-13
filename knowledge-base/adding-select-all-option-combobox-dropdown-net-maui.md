---
title: Adding Select All Option in ComboBox Drop-Down
description: Learn how to add a Select All option in the drop-down list of a ComboBox for .NET MAUI.
type: how-to
page_title: How to Add Select All Option in ComboBox Drop-Down - ComboBox for .NET MAUI
slug: adding-select-all-option-combobox-dropdown-net-maui
tags: combobox, dropdown, select all, .NET MAUI
res_type: kb
---

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | Telerik UI for .NET MAUI ComboBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

To add a **Select All** option in the dropdown list of a Telerik UI for .NET MAUI ComboBox, follow the steps below.

## Solution

**1.** Define the `HeaderTemplate` for the ComboBox control. The `HeaderTemplate` should contain a `CheckBox` that represents the **Select All** option.

```XAML
<telerik:RadComboBox 
    x:Name="comboBox"
    ItemsSource="{Binding Items}"
    SelectionMode="Multiple"
    IsEditable="True"
    DisplayMemberPath="Name"
    SelectedItems="{Binding SelectedItems}"
    AutomationId="comboSelectedItemMultiple"
    WidthRequest="200">
    <telerik:RadComboBox.HeaderTemplate>
        <DataTemplate>
            <HorizontalStackLayout>
                <telerik:RadCheckBox IsCheckedChanged="RadCheckBox_IsCheckedChanged"/>
                <Label Text="Select All"/>
            </HorizontalStackLayout>
        </DataTemplate>
    </telerik:RadComboBox .HeaderTemplate>
</telerik:RadComboBox >
```

**2.** Handle the `IsCheckedChange` event of the `CheckBox` in the `HeaderTemplate`. In the event handler, execute the ComboBox's `SelectAllCommand` when the checkbox is checked, and execute the ComboBox's `ClearSelectionCommand` when the checkbox is unchecked.

```C#
private void RadCheckBox_IsCheckedChanged(object sender, IsCheckedChangedEventArgs e)
{
    RadCheckBox cb = (RadCheckBox)sender;
    MyComboBox mcb = GetMyComboBox(cb);

    if (cb.IsChecked.HasValue && cb.IsChecked.Value)
    {
        mcb.SelectAllCommand.Execute(null);
    }
    else
    {
        mcb.ClearSelectionCommand.Execute(null);

    }
}

private static MyComboBox GetMyComboBox(Element element)
{
    if (element is MyComboBox myComboBox1)
    {
        return myComboBox1;
    }

    if (element == null)
    {
        return null;
    }

    return GetMyComboBox(element.Parent); //get ComboBox control recursively
}
```

That's it! You have successfully added a **Select All** option in the drop-down list of the ComboBox for .NET MAUI.

>tip Next, customize the appearance of the **Select All** option to match your application's design.

If you want to use a command when the CheckBox state changes, review the [Implementing the CheckBoxUserCommand Behavior When Migrating from Xamarin CheckBox to MAUI CheckBox]({%slug migrating-xamarin-checkbox-maui-checkbox%}) how-to article. 

## See Also

- [ComboBox Documentation]({%slug combobox-overview%})