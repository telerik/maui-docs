---
title: Migrating to SegmentedControl after 14.0.0 version
meta_title: Migrating the SegmentedControl after 14.0.0 version of Telerik UI for .NET MAUI
description: Learn how to migrate to the new SegmentedControl released in Telerik UI for .NET MAUI 14.0.0 version&mdash;updated API, data binding, selection, and styling.
slug: segmented-migration
position: 30
---

# Migrating the SegmentedControl after 14.0.0 Version

In the **Telerik UI for .NET MAUI 14.0.0** release, the `RadSegmentedControl` was rebuilt from the ground up. The control keeps its name and core purpose&mdash;display a list of horizontally aligned, mutually exclusive options&mdash;but exposes a new API surface, extended styling options, and additional features such as full data binding, selection modes, item templates, size modes, and per-segment commands.

This article lists the differences between the previous `RadSegmentedControl` (versions before 14.0.0) and the new `RadSegmentedControl` (versions 14.0.0 and later) so you can update existing applications.

## Items and Data Binding

The previous SegmentedControl populated its items only through `ItemsSource` and rendered each item as text by calling `ToString()` on the bound object. The new control also supports the `ItemsSource` property but adds full data binding through `DisplayMemberPath`, `ItemTemplate`, and `DataTemplateSelector` (assigned to `ItemTemplate`).

| Previous SegmentedControl | New SegmentedControl |
| --- | --- |
| `ItemsSource` (string or primitive collection rendered as `ToString()`) | `ItemsSource` (any collection of business objects) |
| - | `DisplayMemberPath`&mdash;path to the property of the business object that is rendered as text |
| - | `ItemTemplate` (`DataTemplate`)&mdash;custom content for each segment |
| - | `ItemTemplate` (`DataTemplateSelector`)&mdash;per-item template selection |

Previous SegmentedControl:

```XAML
<telerik:RadSegmentedControl>
    <telerik:RadSegmentedControl.ItemsSource>
        <x:Array Type="{x:Type x:String}">
            <x:String>Popular</x:String>
            <x:String>Library</x:String>
            <x:String>Playlists</x:String>
            <x:String>Friends</x:String>
        </x:Array>
    </telerik:RadSegmentedControl.ItemsSource>
</telerik:RadSegmentedControl>
```

New SegmentedControl bound to:

An array of strings:

```XAML
<telerik:RadSegmentedControl>
    <telerik:RadSegmentedControl.ItemsSource>
        <x:Array Type="{x:Type x:String}">
            <x:String>Popular</x:String>
            <x:String>Library</x:String>
            <x:String>Playlists</x:String>
            <x:String>Friends</x:String>
        </x:Array>
    </telerik:RadSegmentedControl.ItemsSource>
</telerik:RadSegmentedControl>
```

A collection of business objects through `DisplayMemberPath` and `ItemsSource` properties:

```XAML
<telerik:RadSegmentedControl ItemsSource="{Binding FileCategories}"
                             DisplayMemberPath="Category" />
```

New SegmentedControl with a custom `ItemTemplate`:

```XAML
<telerik:RadSegmentedControl ItemsSource="{Binding FileCategories}">
    <telerik:RadSegmentedControl.ItemTemplate>
        <DataTemplate>
            <VerticalStackLayout Spacing="10">
                <Label Text="{Binding Icon}"
                       FontFamily="TelerikFontExamples" />
                <Label Text="{Binding Category}"
                       FontSize="10" />
            </VerticalStackLayout>
        </DataTemplate>
    </telerik:RadSegmentedControl.ItemTemplate>
</telerik:RadSegmentedControl>
```

For more details, see the [Data Binding]({%slug segmentedcontrol-data-binding%}) article.

## Selection

The previous SegmentedControl always operated in single-selection mode. The new SegmentedControl exposes a `SelectionMode` property and supports two-way binding for both `SelectedIndex` and `SelectedItem`.

| Previous SegmentedControl | New SegmentedControl |
| --- | --- |
| `SelectedIndex` (`int`) | `SelectedIndex` (`int`) |
| `SelectedItem` (`object`) | `SelectedItem` (`object`) |
| - | `SelectionMode` (`SegmentedControlSelectionMode`): `None`, `Single`, `SingleDeselect` |
| `SelectionChanged` event with `ValueChangedEventArgs<int>` | `SelectionChanged` event with `RadSelectionChangedEventArgs` |

```XAML
<telerik:RadSegmentedControl ItemsSource="{Binding Categories}"
                             SelectedItem="{Binding SelectedItem, Mode=TwoWay}"
                             SelectedIndex="{Binding SelectedIndex, Mode=TwoWay}"
                             SelectionMode="SingleDeselect"
                             SelectionChanged="OnSelectionChanged" />
```

For more details, see the [Selection]({%slug segmentedcontrol-selection%}) article.

## Item Tapped

The new SegmentedControl raises an `ItemTapped` event and exposes an `ItemTappedCommand`. They are fired regardless of the current selection, which allows you to react to taps even when the user taps an already-selected segment.

| Previous SegmentedControl | New SegmentedControl |
| --- | --- |
| - | `ItemTapped` event |
| - | `ItemTappedCommand` (`ICommand`) |

For more details, see the [Item Tapped]({%slug segmentedcontrol-item-tapped%}) article.

## Disabled Segments

There isn't any change in the API for disabling segments. The new SegmentedControl still provides the `SetSegmentEnabled(int index, bool isEnabled)` and `IsSegmentEnabled(int index)` methods to disable segments and check their state.

| Previous SegmentedControl | New SegmentedControl |
| --- | --- |
| `SetSegmentEnabled(int index, bool isEnabled)` method | `SetSegmentEnabled(int index, bool isEnabled)` method |
| `IsSegmentEnabled(int index)` method | `IsSegmentEnabled(int index)` method |

```C#
this.segmentControl.SetSegmentEnabled(2, false);
```

For more details, see the [Disabled Segments]({%slug segmentedcontrol-disable-segment%}) article.

## Size Mode

The new SegmentedControl introduces a `SizeMode` property at the item view level that defines how each segment sizes itself within the control. The previous version did not provide a dedicated sizing API.

| Previous SegmentedControl | New SegmentedControl |
| --- | --- |
| - | `RadSegmentedControlItemView.SizeMode` (`SegmentedControlSizeMode`): `Star`, `Auto`, `Fixed` |

```XAML
<telerik:RadSegmentedControl.ItemViewStyle>
    <Style TargetType="telerik:RadSegmentedControlItemView">
        <Setter Property="SizeMode" Value="Auto" />
    </Style>
</telerik:RadSegmentedControl.ItemViewStyle>
```

For more details, see the [Size Mode]({%slug segmentedcontrol-size-mode%}) article.

## Styling

The styling pipeline has been completely redesigned. The previous version exposed a small set of color properties directly on the control. The new SegmentedControl inherits from `RadBorder` for the surrounding frame and uses dedicated `Style` properties that target the new visual elements&mdash;`RadSegmentedControlItemView`, the selection indicator, and the separator.

### Control-Level Properties

The previous color properties on the control are replaced by `Style` properties and by the appearance properties of the `RadBorder` base type.

| Previous SegmentedControl | New SegmentedControl |
| --- | --- |
| `SegmentBackgroundColor` | `ItemViewStyle` &rarr; `BackgroundColor` setter |
| `SegmentTextColor` | `ItemViewStyle` &rarr; `TextColor` setter |
| `SelectedSegmentBackgroundColor` | `SelectionIndicatorStyle` &rarr; `BackgroundColor` setter |
| `SelectedSegmentTextColor` | `ItemViewStyle` &rarr; `SelectedTextColor` setter |
| `DisabledSegmentTextColor` | `ItemViewStyle` (visual states for the disabled state) |
| - | `BorderColor`, `BackgroundColor`, `BorderThickness`, `CornerRadius`, `Padding` (inherited from `RadBorder`) |
| - | `ItemViewStyle` (`Style` with `TargetType="telerik:RadSegmentedControlItemView"`) |
| - | `ItemViewStyleSelector` (`IStyleSelector`) |
| - | `SelectionIndicatorStyle` (`Style` with `TargetType="telerik:RadBorder"`) |
| - | `SeparatorStyle` (`Style` with `TargetType="telerik:RadBorder"`) |

### Item View Properties

The new `RadSegmentedControlItemView` element exposes a rich set of bindable properties that were not available on the previous control:

* `TextColor`, `SelectedTextColor`
* `BackgroundColor`, `BorderColor`, `BorderThickness`, `CornerRadius`, `Padding`
* `FontSize`, `FontFamily`, `FontAttributes`
* `HorizontalTextAlignment`, `VerticalTextAlignment`
* `SizeMode`

### Migrating the Styling Setup

Previous SegmentedControl:

```XAML
<telerik:RadSegmentedControl SegmentBackgroundColor="#0D8660C5"
                             SegmentTextColor="#8660C5"
                             SelectedSegmentBackgroundColor="#8660C5"
                             SelectedSegmentTextColor="White"
                             DisabledSegmentTextColor="Gray" />
```

New SegmentedControl:

```XAML
<ContentView.Resources>
    <Style x:Key="SegmentItemView" TargetType="telerik:RadSegmentedControlItemView">
        <Setter Property="TextColor" Value="#8660C5" />
        <Setter Property="SelectedTextColor" Value="White" />
        <Setter Property="BackgroundColor" Value="#0D8660C5" />
        <Setter Property="FontAttributes" Value="Bold" />
    </Style>
    <Style x:Key="SelectedSegmentIndicatorStyle" TargetType="telerik:RadBorder">
        <Setter Property="BackgroundColor" Value="#8660C5" />
        <Setter Property="CornerRadius" Value="4" />
        <Setter Property="Padding" Value="2" />
    </Style>
    <Style x:Key="SegmentSeparatorStyle" TargetType="telerik:RadBorder">
        <Setter Property="WidthRequest" Value="2" />
        <Setter Property="BackgroundColor" Value="Gray" />
        <Setter Property="Margin" Value="2" />
    </Style>
</ContentView.Resources>

<telerik:RadSegmentedControl ItemViewStyle="{StaticResource SegmentItemView}"
                             SelectionIndicatorStyle="{StaticResource SelectedSegmentIndicatorStyle}"
                             SeparatorStyle="{StaticResource SegmentSeparatorStyle}"
                             BorderColor="#8660C5"
                             BackgroundColor="#0D8660C5"
                             CornerRadius="20" />
```

For per-item styling, the new control supports an `ItemViewStyleSelector` of type `IStyleSelector`, which has no equivalent in the previous version.

For more details, see the [Styling]({%slug segmentedcontrol-styling%}) article.

## Additional Features

The new SegmentedControl also adds the following capabilities that did not exist in the previous version:

* **Right-to-left support**&mdash;The control mirrors its layout when `FlowDirection` is set to `RightToLeft`.
* **Keyboard navigation**&mdash;Users can move between segments and change the selection through the keyboard on platforms that support it.
* **Visual states**&mdash;The new item view participates in the .NET MAUI `VisualStateManager`, which allows full control of the appearance for the normal, selected, disabled, and focused states.

## API Differences Summary

The following table summarizes the API differences between the previous and the new SegmentedControl:

| Area | Previous SegmentedControl | New SegmentedControl |
| --- | --- | --- |
| Base type | `View` | `RadBorder` |
| Items | `ItemsSource` only | `ItemsSource`, `DisplayMemberPath`, `ItemTemplate`, `DataTemplateSelector` |
| Selection | `SelectedIndex`, `SelectedItem`, `SelectionChanged` | `SelectedIndex`, `SelectedItem`, `SelectionMode`, `SelectionChanged` |
| Tapping | - | `ItemTapped`, `ItemTappedCommand` |
| Disable item | `DisabledSegmentTextColor` only | `SetSegmentEnabled`, `IsSegmentEnabled` |
| Sizing | - | `RadSegmentedControlItemView.SizeMode` (`Star`, `Auto`, `Fixed`) |
| Styling | `SegmentBackgroundColor`, `SegmentTextColor`, `SelectedSegmentBackgroundColor`, `SelectedSegmentTextColor`, `DisabledSegmentTextColor` | `ItemViewStyle`, `ItemViewStyleSelector`, `SelectionIndicatorStyle`, `SeparatorStyle`, plus `RadBorder` appearance properties |
| RTL | - | Supported through `FlowDirection` |
| Keyboard | - | Supported |

## See Also

- [Overview]({%slug segmentedcontrol-overview%})
- [Getting Started]({%slug segmentedcontrol-getting-started%})
- [Data Binding]({%slug segmentedcontrol-data-binding%})
- [Selection]({%slug segmentedcontrol-selection%})
- [Item Tapped]({%slug segmentedcontrol-item-tapped%})
- [Disabled Segments]({%slug segmentedcontrol-disable-segment%})
- [Size Mode]({%slug segmentedcontrol-size-mode%})
- [Styling]({%slug segmentedcontrol-styling%})


