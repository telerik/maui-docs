---
title: Entry
page_title: .NET MAUI Toolbar Documentation - Entry ToolbarItem
description: Review the entry Toolbar item for .NET MAUI.
position: 1
slug: toolbar-items-entry
---

# .NET MAUI Entry ToolbarItem 

Add input fields in the toolbar using the `EntryToolbarItem`.

The available properties for configuration are:

* `Text`(`string`)&mdash;Defines the text(target type `Label`) in the toolbar item. You can display an image next to the text.

## Events

* `TextChanged`&mdash;Raised when the `EntryToolbarItem.Text` property has changed.
* `EntryCompleted`&mdash;Raised when the user finalizes the text in the `Microsoft.Maui.Controls.Entry` control with the return key.

## Styling

You can style the `EntryToolbarItem` using the following property:

* `EntryStyle` property. The target type of the property is the [Entry](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/entry) control.

> All properties available for customizing and styling the [Entry](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/entry) are applicable for EntryToolbarItem.

Some of the properties are:

* `TextColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Specifies the color of the text in the toolbar item.
* `Placeholder`(`string`)&mdash;Specifies the text that is displayed when the control is empty.
* `PlaceholderColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Specifies the color of the text that is displayed when the control is empty.
* `FontFamily`(`string`)&mdash;Specifies the font family of the text to display in the toolbar item.
* `FontAutoScalingEnabled`(`bool`)&mdash;Determines whether the font of the entry scales automatically according to the operating system settings. Default value is true.
* `FontSize`(`double`)&mdash;Specifies the font size of the text to display in the toolbar item.
* `FontAttributes`(enum of type `Microsoft.Maui.Controls.FontAttributes`)&mdash;Defines the font attributes of the text to display in the toolbar item. Default value is `None`.
* `HorizontalTextAlignment`(enum of type `Microsoft.Maui.TextAlignment`)&mdash;Defines the horizontal alignment of the text to display in the toolbar item. The default value is `Start`.
* `VerticalTextAlignment`(enum of type `Microsoft.Maui.TextAlignment`)&mdash;Defines the vertical alignment of the text to display in the toolbar item. Default value is `Center`.
* `HorizontalOptions`(enum of type `Microsoft.Maui.Controls.LayoutOptions`)&mdash;Specifies the horizontal alignment options of the content displayed in the toolbar item.
* `VerticalOptions`(enum of type `Microsoft.Maui.Controls.LayoutOptions`)&mdash;Specifies the vertical alignment options of the content displayed in the toolbar item.

### Example with EntryToolbarItem Styling

**1.** The style applied in the resources:

```XAML
<Style TargetType="Entry" x:Key="entryStyle">
    <Setter Property="Placeholder" Value="EntryToolbar"/>
</Style>
```

**2.** The EntryToolbarItem definition:

```XAML
 <telerik:EntryToolbarItem EntryStyle="{StaticResource entryStyle}"/>
```

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})
