---
title: BusyIndicator
page_title: .NET MAUI Toolbar Documentation - BusyIndicator ToolbarItem
description: Review the busy indicator Toolbar item for .NET MAUI.
position: 1
slug: toolbar-items-busy0indicator
---

# .NET MAUI BusyIndicator ToolbarItem 

Add busy indicators in the toolbar using the `BusyIndicatorToolbarItem`.

The available properties for configuration are:

* `IsBusy`(`bool`)&mdash;Specifies whether the busy indicator is busy. 

## Styling

You can style the `BusyIndicatorToolbarItem` using the `Style` property. The target type of the property is `BusyIndicatorToolbarItemView`. 

> All properties available for customizing and styling the [RadBusyIndicator]({%slug busyindicator-overview%}) are applicable for BusyIndicatorToolbarItem.

### Example with BusyIndicatorToolbarItem Styling

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
