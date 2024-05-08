---
title: Migrating from Xamarin
page_title: Migrating the ImageEditor from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin ImageEditor to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
position: 20
slug: imageeditor-migrate-from-xamarin
---

# Migrating the ImageEditor from Xamarin to .NET MAUI

Telerik .NET MAUI ImageEditor control preserves the same API as Xamarin.Forms ImageEditor with a few changes and improvements listed in the tables below:

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin ImageEditor | `RadImageEditor` | xmlns:telerikImageEditor="clr-namespace:Telerik.XamarinForms.ImageEditor;assembly=Telerik.XamarinForms.ImageEditor" | using Telerik.XamarinForms.ImageEditor; |
| Xamarin ImageEditorToolbar | `RadImageEditorToolbar` | xmlns:telerikImageEditor="clr-namespace:Telerik.XamarinForms.ImageEditor;assembly=Telerik.XamarinForms.ImageEditor" | using Telerik.XamarinForms.ImageEditor; |
| .NET MAUI ImageEditor | `RadImageEditor` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |
| .NET MAUI ImageEditorToolbar | `RadImageEditorToolbar` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |


## Modifying the API

When migrating the ImageEditor from Xamarin to .NET MAUI, consider the following differences in the API:

| Xamarin ImageEditor | .NET MAUI ImageEditor |
| ------------- | --------------- |
| N/A | support for exporting images as `Gif` |
| N/A | support for exporting images as `Bmp` |
| N/A | `UndoCommand` |
| N/A | `RedoCommand` |
| N/A | `RotateBackwardCommand` |
| N/A | `SaturationInteractiveCommand` |
| N/A | `BrightnessInteractiveCommand` |
| N/A | `BlurInteractiveCommand` |
| N/A | `ContrastInteractiveCommand` |
| N/A | `HueInteractiveCommand` |
| N/A | `SharpenInteractiveCommand` |

When migrating the ImageEditorToolbar from Xamarin to .NET MAUI, consider the following differences in the API:

| Xamarin ImageEditorToolbar | .NET MAUI ImageEditorToolbar |
| ------------- | --------------- |
| `IsMultiLine` with `true` and `false` values | `OverflowMode` with `DropDown`, `Scroll` and `Wrap`(multiline) values  |
| N/A | `OverflowMenuButtonVisibility` |
| `OverflowButtonTemplate` | `OverflowMenuButtonTemplate` |
| `OverflowButtonText`, `OverflowButtonTextColor` and `OverflowButtonFontFamily` | `OverflowMenuButtonStyle` - Style the overflow button |
| `TransformsToolbarItem` | `ImageEditorTransformationsToolbarItem` |
| `CropToolbarItem` for mobile and desktop | `ImageEditorCropToolbarItem` |
| N/A | `ImageEditorCropOptionsToolbarItem` |
| `ResizeToolbarItem` | `ImageEditorResizeOptionsToolbarItem` |
| `RotateLeftToolbarItem` | `ImageEditorRotateLeftToolbarItem` |
| `RotateRightToolbarItem` | `ImageEditorRotateRightToolbarItem` |
| `FlipHorizontalToolbarItem` | `ImageEditorFlipHorizontalToolbarItem` |
| `FlipVerticalToolbarItem` | `ImageEditorFlipVerticalToolbarItem` |
| `EffectsToolbarItem` for mobile and desktop | `ImageEditorFiltersToolbarItem` for mobile |
| N/A | `ImageEditorFilterOptionsToolbarItem` for desktop |
| `TransformsToolbarItem` | `ImageEditorTransformationsToolbarItem` |
| `HueToolbarItem` | `ImageEditorHueToolbarItem` |
| `SaturationToolbarItem` | `ImageEditorSaturationToolbarItem` |
| `BrightnessToolbarItem` | `ImageEditorBrightnessToolbarItem` |
| `ContrastToolbarItem` | `ImageEditorContrastToolbarItem` |
| `BlurToolbarItem` | `ImageEditorBlurToolbarItem` |
| `SharpenToolbarItem` | `ImageEditorSharpenToolbarItem` |
| `UndoToolbarItem` | `ImageEditorUndoToolbarItem` |
| `RedoToolbarItem` | `ImageEditorRedoToolbarItem` |
| `ResetToolbarItem` | `ImageEditorResetToolbarItem` |
| `ApplyToolbarItem` | `ImageEditorApplyToolbarItem` |
| `CancelToolbarItem` | `ImageEditorCancelToolbarItem` |
| `TemplateToolbarItem` | Review the [toolbar items]({%slug toolbar-items%}) `RadToolbar` control provides |
| `CommandToolbarItem` | Review the [toolbar items]({%slug toolbar-items%}) `RadToolbar` control provides |
| `ZoomToFitToolbarItem` | `ImageEditorZoomToFitToolbarItem` |
| N/A | `ImageEditorZoomInToolbarItem` |
| N/A | `ImageEditorZoomOutToolbarItem` |
| N/A | `ImageEditorZoomToolbarItem` |
| N/A | `ImageEditorZoomToOriginalToolbarItem` |

The code snippets below represent the Xamarin and .NET MAUI definitions of the ImageEditor and ImageEditorToolbar with all predefined toolbar items.

```Xamarin
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition />
        <RowDefinition Height="Auto" />
    </Grid.RowDefinitions>
    <telerikImageEditor:RadImageEditor x:Name="imageEditor">
        <telerikImageEditor:RadImageEditor.Source>
            <OnPlatform x:TypeArguments="ImageSource" Default="cat4.jpeg">
                <On Platform="UWP">Assets\cat4.jpeg</On>
            </OnPlatform>
        </telerikImageEditor:RadImageEditor.Source>
    </telerikImageEditor:RadImageEditor>
    <telerikImageEditor:RadImageEditorToolbar Grid.Row="1" ImageEditor="{x:Reference imageEditor}" AutoGenerateItems="False">
        <telerikImageEditor:EffectsToolbarItem AutoGenerateItems="False">
            <telerikImageEditor:BackToolbarItem/>
            <telerikImageEditor:ContrastToolbarItem AutoGenerateItems="False">
                <telerikImageEditor:CancelToolbarItem HorizontalOptions="Start" />
                <telerikImageEditor:TemplateToolbarItem>
                    <telerikImageEditor:TemplateToolbarItem.Template>
                        <DataTemplate>
                            <Slider Maximum="2" Minimum="0" Value="{Binding Value}" />
                        </DataTemplate>
                    </telerikImageEditor:TemplateToolbarItem.Template>
                </telerikImageEditor:TemplateToolbarItem>
                <telerikImageEditor:ApplyToolbarItem HorizontalOptions="End" />
            </telerikImageEditor:ContrastToolbarItem>
        </telerikImageEditor:EffectsToolbarItem>
        <telerikImageEditor:CropToolbarItem/>
        <telerikImageEditor:RotateLeftToolbarItem/>
        <telerikImageEditor:RotateRightToolbarItem/>
        <telerikImageEditor:UndoToolbarItem/>
        <telerikImageEditor:RedoToolbarItem/>
    </telerikImageEditor:RadImageEditorToolbar>
</Grid>
```
```MAUI
<snippet id='imageeditor-commands-xaml'/>
```

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI ImageEditor Product Page](https://www.telerik.com/maui-ui/imageeditor)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
