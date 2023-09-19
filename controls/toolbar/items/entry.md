---
title: Entry
page_title: .NET MAUI Toolbar Documentation - Entry ToolbarItem
description: Learn how to add input fields to the NET MAUI Toolbar by using the Entry Toolbar item. Configure the Entry item by using the emitted events and styling properties.
position: 1
slug: toolbar-items-entry
---

# .NET MAUI Entry ToolbarItem 

Add input fields to the Toolbar by using the `EntryToolbarItem`.

The available configuration property is:

* `Text`(`string`)&mdash;Defines the text (target type `Label`) in the toolbar item. You can display an image next to the text.

## Events

The Entry Toolbar item emits the following events:

* `TextChanged`&mdash;Raised when the `EntryToolbarItem.Text` property has changed.
* `EntryCompleted`&mdash;Raised when the user finalizes the text in the `Microsoft.Maui.Controls.Entry` control by pressing the `Return` key.

## Styling

You can style the `EntryToolbarItem` by using the following property:

* `EntryStyle`—The target type of the property is the [Entry](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/entry) control.

In addition to the `EntryStyle` property that is specific to the Telerik `EntryToolbarItem`, you can also use all properties that are available for customizing and styling the [Entry](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/entry). Some of these properties are:

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

The following example demonstrates how to style the `EntryToolbarItem`.

**1.** Apply the style in the resources:

```XAML
<Style TargetType="Entry" x:Key="entryStyle">
    <Setter Property="Placeholder" Value="EntryToolbar"/>
</Style>
```

**2.** Add the `EntryToolbarItem` definition:

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
