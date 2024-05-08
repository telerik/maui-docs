---
title: Toggle States
page_title: .NET MAUI ToggleButton Documentation - Toggle States
description: Define the toggled, untoggled, or indeterminate state of the Telerik ToggleButton for .NET MAUI.
position: 2
tags: .net maui, telerik toggle button for .net maui, ui for .net maui, toggle button, microsoft .net maui
slug: togglebutton-toggle-states
---

# Toggle States for .NET MAUI ToggleButton

The ToggleButton enables you to define its state as `Checked`, `Unchecked`, or `Indeterminate`.

The state is controlled through the `IsToggled`(`bool?`) property. You can set all states either through the UI or programmatically. The `Indeterminate` state can be applied through the UI only for three-state checkboxes. `IsToggled` property binding mode is `TwoWay`.

* `Toggled` state&mdash;When `IsToggled` is `true`.

* (Default) `Untoggled` state&mdash;When `IsToggled` is `false`.

* `Indeterminate` state&mdash;When `IsToggled` is `null`.

* `IsThreeState` (`bool`)&mdash;Defines whether you can apply the indeterminate state through the UI. When `IsThreeState` is `true`, it allows the end user to go to the indeterminate state along with the `Checked` and `Unchecked` states. By default, `IsThreeState` is `false`.

* The following example demonstrates how to set the `IsThreeState` property.

**1.** Set the `IsThreeState` property of the `RadToggleButton`:`

<snippet id='togglebutton-three-state' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Here is the result:

![.NET MAUI ToggleButton ThreeState](images/checkbox-command.gif)

## Events

* `IsToggledChanged`&mdash;Occurs when the `RadCheckBox.IsToggled` property is changed. The `IsToggledChanged` event handler receives two parameters:
    * The `sender` which is of type `Telerik.Maui.Controls.RadToggleButton`.
    * and `ValueChangedEventArgs`. The `ValueChangedEventArgs` provides the following properties:
        * `NewValue`(`TValue`)&mdash;Gets the new value from the `IsToggled` property.
        * `PreviousValue`(`TValue`)&mdash;Gets the previous value of the `IsToggled` property.

## See Also
