---
title: Migrating from Xamarin to MAUI: Implementing IsCheckedChanged Event in Telerik CheckBox
description: This article provides instructions on how to implement the IsCheckedChanged event in the Telerik MAUI CheckBox when migrating from Xamarin.
type: how-to
page_title: Implementing IsCheckedChanged Event in Telerik CheckBox | MAUI CheckBox
slug: implementing-ischeckedchanged-event-in-telerik-checkbox-maui
tags: xamarin, maui, checkbox, migration, ischeckedchanged
res_type: kb
---

## Environment

| Property | Value |
| --- | --- |
| Product | CheckBox for MAUI |
| Version | 6.7.0 |

## Description

When migrating your Xamarin app to MAUI, you may notice that the CheckBoxUserCommand is missing in the Telerik MAUI CheckBox control. This article provides instructions on how to implement the IsCheckedChanged event as an alternative solution.

## Solution

To implement the IsCheckedChanged event in the Telerik MAUI CheckBox, follow these steps:

1. Add the Telerik MAUI CheckBox control to your XAML file:

```xml
<telerik:RadCheckBox IsCheckedChanged="RadCheckBox_IsCheckedChanged">
    <!-- Your CheckBox content here -->
</telerik:RadCheckBox>
```

2. In your code-behind or ViewModel, create a command that will handle the CheckedChanged event:

```csharp
public ICommand CheckedChangedCommand => new Command<bool>(OnCheckedChanged);

private void OnCheckedChanged(bool isChecked)
{
    // Your logic here
}
```


By following these steps, you can successfully implement the IsCheckedChanged event in the Telerik MAUI CheckBox when migrating your Xamarin app to MAUI.

## See Also

- [Telerik MAUI CheckBox Documentation](https://docs.telerik.com/devtools/maui/controls/checkbox/xamarin-migration)
