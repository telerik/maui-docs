---
title: Keyboard Support
meta_title: .NET MAUI AutoComplete Documentation - Keyboard Support for WinUI and MacCatalyst
description: Learn more about the available keyboard combinations as part of the supported Telerik UI for .NET MAUI AutoComplete accessibility standards.
position: 6
slug: autocomplete-keyboard-support
---

# .NET MAUI AutoComplete Keyboard Support

[Telerik UI for .NET MAUI AutoComplete]({%slug autocomplete-overview%}) provides keyboard navigation support on WinUI and Mac Catalyst.

The following table lists the actions and keyboard combinations that are available in the AutoComplete control:

| Hotkey Combinations  | Action |
| -------------------- | ------ |
| `Tab` | Focuses the control and opens the suggestion view. |
| `Enter` | Commits the selected item from the suggestion view and closes the suggestion view. |
| `Esc`	| Takes effect only when the suggestion view is opened. It closes the suggestion view of the AutoComplete control. |
| `Up Arrow` / `Down Arrow` | When the suggestion view is opened, pressing `Up/Down Arrows` changes the highlighted item in the suggestion view list. |
| `PageUp` / `PageDown` | When the suggestion view is opened, pressing `PageUp/PageDown` changes the highlighted item. `PageUp` navigates to the first item in the visible area, `PageDown` navigates to the last item in the visible area. |
| `Backspace` (WinUI) | When there are tokens in the input area, pressing the `Backspace` key deletes the token. |

The first item in the suggestion view is highlighted by default (set as `CuttentItem`) when the view gets opened.

## See Also

- [Suggest Mode]({%slug autocomplete-suggest-mode%})
- [Display Text]({%slug autocomplete-display-text-formatter%})
- [Tokens Support]({%slug autocomplete-tokens-support%})
- [Remote Search]({%slug autocomplete-remote-search%})
- [Filtering]({%slug autocomplete-filtering%})
- [Events]({%slug autocomplete-events%})
- [Methods]({%slug autocomplete-methods%})
- [Templates]({%slug autocomplete-custom-templates%})
- [Styling]({%slug autocomplete-styling%})
