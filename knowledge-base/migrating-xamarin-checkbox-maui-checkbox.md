---
title: Implementing the CheckBoxUserCommand Behavior When Migrating from Xamarin CheckBox to MAUI CheckBox
description: Learn how to implement the Xamarin CheckBoxUserCommand behavior in MAUI when migrating from Xamarin.
type: how-to
page_title: Migrating the Xamarin Checkbox CheckBoxUserCommand to MAUI
slug: migrating-xamarin-checkbox-maui-checkbox
tags: xamarin, maui, checkbox, migration
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | Telerik UI for .NET MAUI CheckBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

When migrating your Xamarin app to MAUI, you may notice that the CheckBoxUserCommand behavior is missing in the Telerik MAUI CheckBox control. This article will show you how to implement a similar scenario in MAUI.

## Solution

To achieve a similar behavior in MAUI, you can use the `IsCheckedChanged` event along with the `EventToCommandBehavior` from the Microsoft Community Toolkit for MAUI.

**1.** Add the `EventToCommandBehavior` package to your MAUI project. You can find more information on how to do this in the [Microsoft Community Toolkit documentation](https://learn.microsoft.com/en-us/dotnet/communitytoolkit/maui/behaviors/event-to-command-behavior).

**2.** In your MAUI XAML file, add the `RadCheckBox` control and the `EventToCommandBehavior` as a behavior.

```xaml
<telerik:RadCheckBox IsCheckedChanged="RadCheckBox_IsCheckedChanged">
    <telerik:RadCheckBox.Behaviors>
        <toolkit:EventToCommandBehavior EventName="IsCheckedChanged"
                                        Command="{Binding CheckedCommand}" />
    </telerik:RadCheckBox.Behaviors>
</telerik:RadCheckBox>
```

By using the `IsCheckedChanged` event and the `EventToCommandBehavior`, you can achieve a similar behavior to the `CheckBoxUserCommand` in the Xamarin Checkbox control.

## Notes

- Make sure to add the necessary namespaces for the `RadCheckBox` and `EventToCommandBehavior` controls in your XAML file.
- You may need to adjust the event handler or command binding based on your specific implementation.

## See Also

- [Migrating from Xamarin Checkbox to MAUI Checkbox](https://docs.telerik.com/devtools/maui/controls/checkbox/xamarin-migration)
