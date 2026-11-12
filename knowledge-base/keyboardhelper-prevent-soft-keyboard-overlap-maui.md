---
title: Using KeyboardHelper to Prevent Soft Keyboard Overlap in .NET MAUI
description: Learn how to use the Telerik KeyboardHelper attached properties to keep focused input views visible above the soft keyboard on Android and iOS, and to control tab navigation on desktop.
type: how-to
page_title: Prevent Soft Keyboard Overlap with KeyboardHelper in .NET MAUI
meta_title: Prevent Soft Keyboard Overlap with KeyboardHelper in .NET MAUI
slug: keyboardhelper-prevent-soft-keyboard-overlap-maui
tags: keyboardhelper, keyboard, soft keyboard, translation, istabstop, .net maui, android, ios
res_type: kb
---

## Environment

| Product | Author |
| --- | --- |
| Telerik UI for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

On Android and iOS, the soft keyboard can cover an input view, such as an `Entry` or an `Editor`, when the view is close to the bottom of the page. The user then cannot see the text that they type.

The `KeyboardHelper` static class in the `Telerik.Maui.Controls` namespace moves a selected part of the layout up when the keyboard opens, so that the focused view stays visible. The class also exposes an attached property that controls tab navigation on Windows and macOS.

This knowledge base article also answers the following questions:

- How do I prevent the soft keyboard from hiding an `Entry` in .NET MAUI?
- How do I move a layout up when the keyboard opens on Android or iOS?
- What do the `IsTranslationSource`, `IsTranslationTarget`, and `IsTranslationPivot` properties do?
- How do I exclude a Telerik view from tab navigation on Windows or macOS?

## Solution

`KeyboardHelper` works through attached properties. You set the properties on views in XAML or in C#. You do not create an instance of the class.

### KeyboardHelper Attached Properties

The following table lists the public attached properties of `KeyboardHelper`.

| Property | Type | Default | Platforms | Description |
| --- | --- | --- | --- | --- |
| `IsTranslationSource` | `bool` | `False` | Android, iOS | Marks the view that triggers the translation when it receives focus. Set it on the input view, for example an `Entry`. |
| `IsTranslationTarget` | `bool` | `False` | Android, iOS | Marks the view that moves up when the keyboard opens. Set it on a parent layout of the source view. |
| `IsTranslationPivot` | `bool` | `False` | Android, iOS | Marks the view that must stay fully visible above the keyboard. The translation distance depends on the bottom edge of this view. |
| `IsTabStop` | `bool?` | `null` | Windows, macOS | Includes the view in tab navigation (`True`) or excludes it (`False`). When the value is `null`, the platform default applies. |

### How the Translation Works

The translation follows these rules:

1. When a view with `IsTranslationSource="True"` receives focus and the keyboard is visible, `KeyboardHelper` searches the parents of the source view for the nearest view with `IsTranslationTarget="True"`.
1. If the source view is also the target, the source view moves.
1. `KeyboardHelper` selects the pivot in the following order:
    - The first view with `IsTranslationPivot="True"` between the source view and the target view.
    - The target view, if it has `IsTranslationPivot="True"`.
    - The first descendant of the target view with `IsTranslationPivot="True"`.
    - The source view, if no pivot is found.
1. `KeyboardHelper` calculates how far the bottom edge of the pivot is below the top edge of the keyboard. It moves the target up by this distance through a vertical translation.
1. When the source view loses focus or the keyboard closes, the target returns to its original position.

`KeyboardHelper` also updates the translation when the keyboard size changes, or when the size or position of the source, target, or pivot view changes.

> On iOS, the translation is animated with the keyboard animation. On Android, the translation is applied without animation. 
> On Android, `KeyboardHelper` detects the keyboard only when the window is in portrait orientation. In landscape orientation, the target view is not translated.

### Keep an Entry Visible Above the Keyboard

The following example keeps both the `Entry` and the `Send` button visible when the keyboard opens. The `Grid` is the target that moves, the `Entry` is the source, and the inner `HorizontalStackLayout` is the pivot.

1. Add the Telerik namespace to the page:

    ```xml
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

1. Set the attached properties on the views:

    ```xml
    <Grid RowDefinitions="*, Auto"
          telerik:KeyboardHelper.IsTranslationTarget="True">
        <CollectionView Grid.Row="0" ItemsSource="{Binding Messages}" />
        <HorizontalStackLayout Grid.Row="1"
                               Spacing="8"
                               telerik:KeyboardHelper.IsTranslationPivot="True">
            <Entry Placeholder="Type a message"
                   WidthRequest="250"
                   telerik:KeyboardHelper.IsTranslationSource="True" />
            <Button Text="Send" />
        </HorizontalStackLayout>
    </Grid>
    ```

To set the same properties in C#, use the static setter methods:

```csharp
KeyboardHelper.SetIsTranslationTarget(rootGrid, true);
KeyboardHelper.SetIsTranslationPivot(inputPanel, true);
KeyboardHelper.SetIsTranslationSource(messageEntry, true);
```

### Exclude a View from Tab Navigation

On Windows and macOS, set `IsTabStop` to `False` to skip a view when the user presses the `Tab` key:

```xml
<telerik:RadButton Text="Help"
                   telerik:KeyboardHelper.IsTabStop="False" />
```

When `IsTabStop` is `null`, the view is a tab stop on Windows and is not a tab stop on macOS. A disabled view (`IsEnabled="False"`) is never a tab stop, regardless of the `IsTabStop` value. `KeyboardHelper` updates the tab stop state when `IsEnabled` changes.

## Notes

- The translation properties have no effect on Windows and macOS.
- Set the translation properties on views that are loaded in the visual tree. `KeyboardHelper` skips the translation if the source, target, or pivot view is not loaded.
- If the pivot is already above the keyboard, the target does not move.
- `KeyboardHelper` sets the `TranslationY` value of the target view. Avoid setting `TranslationY` on the same view from your own code.

## See Also

- [Handling Keyboard Overlap EditCell in RadDataGrid for .NET MAUI]({%slug prevent-keyboard-overlap-datagrid-maui%})
