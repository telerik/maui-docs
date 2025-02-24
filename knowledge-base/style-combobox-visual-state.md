---
title: Styling ComboBox in Telerik MAUI After Upgrading to Version 8.0.0 or Later
description: Learn how to apply styles to RadComboBox, including border color and thickness, and background color when the control is focused, after upgrading to Telerik MAUI version 8.0.0 or later.
type: how-to
page_title: How to Style ComboBox with Focused State in Telerik MAUI Version 8.0.0+
slug: style-combobox-visual-state-border-telerik-maui
tags: combobox, styling, visual states, telerik, maui, upgrade, focused state
res_type: kb
---

## Environment

| Versions | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 vs. latest | Telerik UI for .NET MAUI ComboBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

After updating my application from Telerik MAUI 7.1.0 to 8.0.0 or a later version, the styles set on `RadComboBox` controls, such as colored borders and backgrounds, disappear when the controls are focused. How can I apply these styles again?

This knowledge base article also answers the following questions:
- How can I apply border color and thickness to `RadComboBox` in Telerik MAUI after an update to 8.0.0 or a later version?
- How do I maintain the `RadComboBox` background color when it's focused in Telerik MAUI version 8.0.0 or later?
- What changes are necessary for styling `RadComboBox` upon focusing after migrating to Telerik MAUI 8.0.0 or later?

## Solution

To style the `RadComboBox` control, including maintaining or altering the border color, thickness, and background color when the control is focused, you need to apply specific styles to the `Focused` visual state of the control. This approach is necessary due to changes in the `RadComboBox` API and the introduction of a new theming mechanism in Telerik MAUI version 8.0.0 and later.

### Set the Focused Visual State

First, familiarize yourself with the [`RadComboBox` Styling]({%slug combobox-styling%}) documentation and the [Visual States]({%slug combobox-visual-states%}) guide. These resources provide essential information on how to style the `RadComboBox` control effectively.

### API Changes from Telerik MAUI 7.1.0 to 8.0.0 and Later

The `RadComboBox` control has changes in the transition from version 7.1.0 to 8.0.0.

The table below summarizes the key changes relevant to styling:

| Telerik.UI.for.MAUI <= 7.1.0 | Telerik.UI.for.MAUI >= 8.0.0 |
| ------------ | ----------- |
| `DropDownButtonStyle` (`Style` with tagtet type `RadButton`) | `DropDownButtonStyle` (`Style` with target type `RadTemplatedButton`). |
| `ClearButtonStyle` (`Style` with tagtet type `RadButton`) |  `ClearButtonStyle` (`Style` with target type `RadTemplatedButton`) and set `TextColor`. |
| NA | [`VisualStates`]({%slug combobox-visual-states%}). |
| Automation Id&mdash;`RadComboBoxEntry`. | Automation Id&mdash;`RadComboBoxTextInput`. |
| NA | `TextInputStyle`&mdash;Allows you to style the inner input control. |

Ensure you review the full list of breaking changes and adapt your application accordingly: [Telerik MAUI 8.0.0 version breaking changes](https://docs.telerik.com/devtools/maui/upgrade/breaking-changes/8-0-0).

By addressing the changes in the API and properly setting the `Focused` visual state, you can maintain or customize the styling of `RadComboBox` controls when they are focused, ensuring a consistent look and feel across your application.

## See Also

- [Telerik UI for MAUI ComboBox Documentation]({%slug combobox-overview%})

