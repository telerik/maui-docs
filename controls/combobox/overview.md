---
title: Overview
page_title: .NET MAUI ComboBox Overview
description: Learn how to use the .NET MAUI ComboBox to select one or more items, search data, style the control, and apply theme-aware appearance settings.
position: 0
slug: combobox-overview
---

# .NET MAUI ComboBox Overview

The Telerik UI for .NET MAUI ComboBox enables users to select one or more items from a dropdown list. It offers various features, including search functionality, options for single and multiple selections, a flexible styling API, and customizable dropdowns, among others.

Use the ComboBox when you want users to choose from a predefined list and optionally search, filter, or select multiple values in the same input area.

![.NET MAUI ComboBox Overview](images/combobox-overview.png "ComboBox Overview")

## Key Features of the .NET MAUI ComboBox

* [Editable and non-editable modes]({%slug combobox-editmode-and-search%})&mdash;The ComboBox supports both editable and non-editable states. When the control is editable, users can type and search.
* [Searching support]({%slug combobox-editmode-and-search%})&mdash;The ComboBox supports `Contains`, `StartsWith`, `ContainsCaseSensitive`, and `StartsWithCaseSensitive` search modes.
* [Single and multiple selection]({%slug combobox-selection%})&mdash;Use the `SelectionMode` property to let users select one item or multiple items.
* [Complex object binding]({%slug combobox-databinding%})&mdash;Use `DisplayMemberPath` to specify which property from a business object is displayed in the control.
* [Filtering support]({%slug combobox-filtering%})&mdash;Users can refine the visible results while they type in the input field.
* [Search highlighting]({%slug combobox-editmode-and-search%})&mdash;The ComboBox highlights the matching text in the dropdown after searching.
* [Placeholder support]({%slug combobox-configuration%}#placeholder)&mdash;Show guidance text when the input is empty or the selected item is cleared.
* [Header and footer templates]({%slug combobox-header-footer%})&mdash;Add custom content above and below the dropdown list through `HeaderTemplate` and `FooterTemplate`.
* [Clear button visibility]({%slug combobox-configuration%}#clearbutton-visibility)&mdash;Control whether users can clear the selection through the built-in clear button.
* [Customizable dropdown]({%slug combobox-configuration%}#dropdown-behavior)&mdash;Control the dropdown width, height, open state, and close-on-selection behavior.
* [Keyboard type]({%slug combobox-configuration%}#keyboard)&mdash;Choose the mobile keyboard layout through the `Keyboard` property.
* [Keyboard navigation]({%slug combobox-keyboard-support%})&mdash;Navigate, open, and close the dropdown with the keyboard on WinUI and MacCatalyst.
* UI virtualization support&mdash;Display large item collections efficiently because the control reuses existing visual items while the dropdown is scrolled.
* [Templates]({%slug combobox-templates%})&mdash;Customize `ItemTemplate`, `SelectedItemTemplate`, `TokenTemplate`, and `ShowMoreTemplate`.
* [Command support]({%slug combobox-commands%})&mdash;Use `ClearSelectionCommand` and `SelectAllCommand` from external UI.
* [Flexible styling API]({%slug combobox-styling%})&mdash;Customize colors, borders, buttons, dropdown appearance, and text presentation.

## Theme-Aware Styling and AppThemeBinding

If you are looking for app theme binding support, use the ComboBox styling properties together with the standard .NET MAUI `AppThemeBinding` markup extension or with Telerik theme resources.

For example, you can apply theme-aware values to properties such as `BackgroundColor`, `BorderColor`, `TextColor`, `PlaceholderColor`, and dropdown styling properties. For control-specific styling options, see [Styling]({%slug combobox-styling%}). For app-wide theme resources and runtime theme switching, see [Theming Overview]({%slug themes-overview%}).

Use the ComboBox styling article when you want to style only this control. Use the theming article when you want the ComboBox appearance to follow your app theme together with other Telerik controls.

## Next Steps

- [Getting Started with Telerik UI for .NET MAUI ComboBox]({%slug combobox-getting-started%})
- [Style the ComboBox]({%slug combobox-styling%})
- [Apply Telerik Themes Across the App]({%slug themes-overview%})

## See Also

- [Visual Structure]({%slug combobox-visual-structure%})
- [Getting Started]({%slug combobox-getting-started%})
- [Configuration]({%slug combobox-configuration%})
- [Data Binding]({%slug combobox-databinding%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})
- [Header and Footer]({%slug combobox-header-footer%})
- [Templates]({%slug combobox-templates%})
- [Styling]({%slug combobox-styling%})
- [Theming Overview]({%slug themes-overview%})
- [.NET MAUI ComboBox Product Page](https://www.telerik.com/maui-ui/combobox)
- [.NET MAUI ComboBox Forum Page](https://www.telerik.com/forums/maui?tagId=1937)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
