---
title: Styling Entry in Telerik MAUI After Upgrading to Version 8.0.0 or Later
description: Learn how to apply styles to RadEntry, including border color and thickness, and background color when the control is focused, after upgrading to Telerik MAUI version 8.0.0 or later.
type: how-to
page_title: How to Style RadEntry with Focused State in Telerik MAUI Version 8.0.0+
slug: style-entry-visual-state-border-telerik-maui
tags: radentry, styling, visual states, telerik, maui, upgrade, focused state
res_type: kb
---

## Environment

| Versions | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 vs. latest | Telerik UI for .NET MAUI RadEntry | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

After updating my application from Telerik MAUI 7.1.0 to 8.0.0 or a later version, the styles set on `RadEntry` controls, such as colored borders and backgrounds, disappear when the controls are focused. How can I apply these styles again?

This knowledge base article also answers the following questions:
- How can I apply border color and thickness to `RadEntry` in Telerik MAUI after an update to 8.0.0 or a later version?
- How do I maintain the `RadEntry` background color when it's focused in Telerik MAUI version 8.0.0 or later?
- What changes are necessary for styling `RadEntry` upon focusing after migrating to Telerik MAUI 8.0.0 or later?

## Solution

To style the `RadEntry` control, including maintaining or altering the border color, thickness, and background color when the control is focused, you need to apply specific styles to the `Focused` visual state of the control. This approach is necessary due to changes in the `RadEntry` API and the introduction of a new theming mechanism in Telerik MAUI version 8.0.0 and later.

### Set the Focused Visual State

First, familiarize yourself with the [`RadEntry` Styling](https://docs.telerik.com/devtools/maui/controls/entry/styling) documentation and the [Visual States](https://docs.telerik.com/devtools/maui/controls/entry/visual-states) guide. These resources provide essential information on how to style the `RadEntry` control effectively.

### API Changes from Telerik MAUI 7.1.0 to 8.0.0 and Later

The `RadEntry` control underwent significant changes in the transition from version 7.1.0 to 8.0.0.

> Prior to version 8.0.0, `RadEntry` inherited directly from Microsoft's MAUI Entry. In version 8.0.0 and later, `RadEntry` is a composite control using the [`RadTextInput`]({%slug entry-textinput%}) control internally for text input.

The table below summarizes the key changes relevant to styling:

| Telerik.UI.for.MAUI <= 7.1.0 | Telerik.UI.for.MAUI >= 8.0.0 |
| ------------ | ----------- |
| `ClearButtonColor` | Set the `TextColor` in the `ClearButtonStyle` (`Style` with target type `RadTemplatedButton`). |
| `HoveredClearButtonColor` | Use `PointerOver` `VisualState` in the `ClearButtonStyle` (`Style` with target type `RadTemplatedButton`) and set `TextColor`. |
| `PressedClearButtonColor` | Use `Pressed` `VisualState` in the `ClearButtonStyle` (`Style` with target type `RadTemplatedButton`) and set `TextColor`. |
| NA | [`VisualStates`]({%slug entry-visual-states%}). |
| `FocusedBorderBrush` | Use the `Focused` `VisualState` and set `BorderBrush`. |
| `FocusedBorderThickness` | Use the `Focused` `VisualState` and set `BorderThickness`. |
| NA | `VisualStates` |
| Automation Id&mdash;`RadEntryEditor`. | Automation Id&mdash;`RadEntryTextInput`. |
| NA | `ValidationErrorColor` |
| NA | `ValidationErrorImageStyle` |
| NA | `ValidationErrorLabelStyle` |

To style the `RadEntry` input area, set the styling properties directly to the `RadEntry`. This approach applies to properties like `Padding`, `MinimumHeightRequest`, `TextColor`, etc.

Ensure you review the full list of breaking changes and adapt your application accordingly: [Telerik MAUI 8.0.0 version breaking changes](https://docs.telerik.com/devtools/maui/upgrade/breaking-changes/8-0-0).

By addressing the changes in the API and properly setting the `Focused` visual state, you can maintain or customize the styling of `RadEntry` controls when they are focused, ensuring a consistent look and feel across your application.

## See Also

- [Telerik UI for MAUI Entry Documentation]({%slug entry-overview%})

