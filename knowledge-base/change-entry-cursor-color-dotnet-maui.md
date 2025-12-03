---
title: Changing Entry Cursor Color on Android and iOS
description: Learn how to change the cursor color of the Entry control on Android and on iOS to match the application's input field styling.
type: how-to
page_title: Adjusting Cursor Color for Entry Control in UI for .NET MAUI
meta_title: Adjusting Cursor Color for Entry Control in UI for .NET MAUI
slug: change-entry-cursor-color-dotnet-maui
tags: entry, ui for .net maui, cursor color, android, radtextinput, handlerchanged, native customization
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 8.0.0 and above | Telerik UI for .NET MAUI Entry | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I am trying to change the cursor color of the [UI for .NET MAUI Entry ](https://www.telerik.com/maui-ui/documentation/controls/entry/overview) control on Android and on iOS to match the color of other input fields in the application. However, the available documentation for customizing the cursor is for versions 5.2.0 to 7.0.0 and is incompatible with the current version. Since version 8.0.0, the control uses `RadTextInput` internally instead of `RadEntry`, which requires different logic for cursor customization.

This knowledge base article also answers the following questions:
- How to update Entry cursor color on mobile?
- How to handle breaking changes for cursor customization in Entry after version 8.0.0?
- How to apply native logic to change cursor color in Entry control?

## Solution

To modify the cursor color in the Entry control, follow these steps:

1. Handle the `Loaded` event of the Entry control to locate the internal `RadTextInput` control and apply the necessary native logic.
2. Use the `Handler` property of `RadTextInput` to update the cursor color for Android and iOS.

```csharp
private void entry_Loaded(object sender, EventArgs e)
{
    var textInput = ChildOfType<RadTextInput>(this.entry);
    if (textInput != null)
    {
        var handler = textInput.Handler;
        if (handler == null)
        {
            textInput.HandlerChanged += this.OnTextInputHandlerChanged;
        }
        else
        {
            this.UpdateNativeElement(handler);
        }
    }
}

private void OnTextInputHandlerChanged(object sender, EventArgs e)
{
    var textInput = (RadTextInput)sender;
    this.UpdateNativeElement(textInput.Handler);
    textInput.HandlerChanged -= this.OnTextInputHandlerChanged;
}

private void UpdateNativeElement(IViewHandler handler)
{
    var nativeEntry = handler.PlatformView as Telerik.Maui.Platform.RadMauiTextInput;
    if (nativeEntry != null)
    {
#if ANDROID
        nativeEntry.TextCursorDrawable?.SetColorFilter(new Android.Graphics.PorterDuffColorFilter(Android.Graphics.Color.Red, Android.Graphics.PorterDuff.Mode.Darken));
#elif __IOS__
        nativeEntry.TintColor = UIKit.UIColor.Red;
#endif
    }
}

internal static T ChildOfType<T>(View visualElement) where T : View
{
    if (visualElement == null)
    {
        return null;
    }

    foreach (var item in VisualTreeElementExtensions.GetVisualTreeDescendants(visualElement))
    {
        if (item is T targetElement)
        {
            return targetElement;
        }
    }

    return null;
}
```

3. Add sample Entry definition in XAML:

```xaml
<VerticalStackLayout>
    <telerik:RadEntry x:Name="entry"
                             Loaded="entry_Loaded" />
</VerticalStackLayout>
```


## See Also

- [Breaking Changes in UI for .NET MAUI 8.0.0](https://www.telerik.com/maui-ui/documentation/upgrade/breaking-changes/8-0-0)
- [Feature Request: Change Cursor Color in Entry](https://feedback.telerik.com/maui/1609886-entry-provide-an-option-to-change-the-cursor-caret-color)
- [UI for .NET MAUI Entry Overview](https://www.telerik.com/maui-ui/components/entry/overview)

