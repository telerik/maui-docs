---
title: BusyIndicator
page_title: .NET MAUI Toolbar Documentation - BusyIndicator Toolbar Item
description: Learn how to add and style the busy indicators when working with the Toolbar for .NET MAUI.
position: 1
slug: toolbar-items-busy0indicator
---

# .NET MAUI BusyIndicator Toolbar Item 

Add busy indicators in the toolbar by using the `BusyIndicatorToolbarItem`.

The available configuration property is:

* `IsBusy`(`bool`)&mdash;Specifies whether the busy indicator is busy. 

## Styling

You can style the `BusyIndicatorToolbarItem` by using the `Style` property. The target type of the property is `BusyIndicatorToolbarItemView`. 

In addition, all properties that are available for customizing and styling the [RadBusyIndicator]({%slug busyindicator-overview%}) are also applicable for `BusyIndicatorToolbarItem`.

The following example demonstrates how to style the `BusyIndicatorToolbarItem`.

**1.** The style applied in the resources:

```XAML
<Style TargetType="telerik:RadBusyIndicator" x:Key="busy">
    <Setter Property="AnimationContentColor" Value="Red"/>
    <Setter Property="AnimationType" Value="Animation3"/>
</Style>
            
<Style TargetType="telerik:BusyIndicatorToolbarItemView" x:Key="busyStyle">
    <Setter Property="BusyIndicatorStyle" Value="{StaticResource busy}"/>
</Style>
```

**2.** The BusyIndicatorToolbarItem definition:

```XAML
<telerik:BusyIndicatorToolbarItem IsBusy="True" Style="{StaticResource busyStyle}"/>
```

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})
