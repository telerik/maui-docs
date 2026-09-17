---
title: Styling
page_title: .NET MAUI Toolbar Documentation - Styling
description: Review all styling options the Telerik .NET MAUI Toolbar provides.
components: ["toolbar"]
position: 14
slug: toolbar-styling
---

# .NET MAUI Toolbar Styling

You can style the Toolbar using the Flexible Styling API.

## Style the toolbar

Style the Toolbar using the following properties:

* `BackgroundColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Specifies the background color of the toolbar.
* `BorderColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Specifies the color of the border around the toolbar.
* `BorderThickness`(`Microsoft.Maui.Thickness`)&mdash;Specifies the thickness of the border around the toolbar.
* `CornerRadius`(`Microsoft.Maui.Thickness`)&mdash;Specifies the corner radius of the border around the toolbar.
* `Style`(of type `Microsoft.Maui.Controls.Style`)&mdash;Specifies the style of the toolbar. 

## Style the toolbar elements

* `OverflowMenuButtonStyle`(`Microsoft.Maui.Controls.Style` with target type `Telerik.Maui.Controls.OverflowMenuButtonToolbarItemView`)&mdash;Specifies the Style applied to the overflow menu button in the toolbar. 
* `BackNavigationButtonStyle`(`Microsoft.Maui.Controls.Style` with target type `Telerik.Maui.Controls.BackNavigationButtonToolbarItemView`)&mdash;Specifies the Style applied to the back navigation button in the toolbar. 
* `ScrollForwardButtonStyle`(`Microsoft.Maui.Controls.Style` with target type `Telerik.Maui.Controls.ScrollForwardButtonToolbarItemView`)&mdash;Specifies the Style applied to the scroll button in the toolbar. 
* `ScrollBackwardButtonStyle`(`Microsoft.Maui.Controls.Style` with target type `Telerik.Maui.Controls.ScrollBackwardButtonToolbarItemView`)&mdash;Specifies the Style applied to the backward scroll button in the toolbar. 

## Styling the toolbar items

@[template](/_contentTemplates/controls/toolbar.md#toolbar-styling)

## Example

Use visual states in the toolbar items to change their appearance when they are in different states. For example, you can change the background color of a button when it is pressed or hovered over.

1. Define the toolbar items in XAML:

<snippet id='toolbar-visual-states'/>

2. Define the `telerik` namespace:

```
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

3. Define the visual states for the toolbar items in XAML:

>caption For `ButtonToolbarItem`, `DropDownButtonToolbarItem`, `ListPickerToolbarItem`, `OptionsButtonToolbarItem`, and `NavigationButtonToolbarItem`:

<snippet id='toolbar-visual-states-button-style'/>

>caption For `LabelToolbarItem`:

<snippet id='toolbar-visual-states-label-style'/>

>caption For `EntryToolbarItem`:

<snippet id='toolbar-visual-states-entry-style'/>

>caption For `ToggleButtonToolbarItem` and `RadioButtonToolbarItem`:

<snippet id='toolbar-visual-states-selectable-style'/>

>caption For `SplitButtonToolbarItem`:

<snippet id='toolbar-visual-states-splitbutton-style'/>

>caption For `OverflowMenuButtonToolbarItem`:

<snippet id='toolbar-visual-states-overflow-menu-button-style'/>

>caption For `BusyIndicatorToolbarItem`:

<snippet id='toolbar-visual-states-busyindicator-style'/>

> For a runnable example with the Toolbar Visual States, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Toolbar > Visual States** category.

## See Also

- [Toolbar Items]({%slug toolbar-items%})
- [Commands]({%slug toolbar-commands%})
