---
title: Ensuring CollectionView Scrollbar is Always Visible on Android in MAUI
description: This article demonstrates how to make the CollectionView's scrollbar always visible on Android 
type: how-to
page_title: How to Keep the CollectionView Scrollbar Always Visible on Android
slug: collectionview-scrollbar-visible-android
tags: collectionview, scrollbar, android, visible, maui, 
res_type: kb
---

## Environment

<table>
<tbody>
<tr>
<td>Product</td>
<td>CollectionView for .NET MAUI</td>
</tr>
<tr>
<td>Version</td>
<td>7.1.0</td>
</tr>
</tbody>
</table>

## Description

Currently the CollectionView's scrollbars are not be visible by default on Android devices. There is a requirement to make the scrollbar always visible to enhance user experience.

This KB article also answers the following questions:
- How to enable the vertical scrollbar in CollectionView on Android?
- How to customize the scrollbar appearance in a MAUI CollectionView on Android?
- How to use a custom drawable for the scrollbar thumb in Android MAUI applications?

## Solution

To make the CollectionView's scrollbar always visible on Android, follow these steps:

### 1. Create the Scrollbar Thumb Drawable

First, create a thumb drawable for the scrollbar in the Android project's Resources -> drawable folder. Name this file "scrollview_thumb.xml". Here is an example of how the XML content might look:

```xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
       android:shape="rectangle" >
  <corners android:radius="4dp" />
  <solid android:color="@color/customColorScrollbar"/>
</shape>
```

Ensure that the build action of this file is set to "MauiXaml".

### 2. Configure the ScrollView handler

Access the native ScrollView through a mapper to the ScrollViewHandler and apply the necessary configurations to make the scrollbar visible:

```csharp
Microsoft.Maui.Handlers.ScrollViewHandler.Mapper.AppendToMapping("MyCustom", (handler, view) => {

#if ANDROID
    handler.PlatformView.VerticalScrollBarEnabled = true;
    handler.PlatformView.ScrollBarStyle = Android.Views.ScrollbarStyles.OutsideOverlay;
    handler.PlatformView.VerticalScrollbarThumbDrawable = AndroidX.AppCompat.Content.Res.AppCompatResources.GetDrawable(Microsoft.Maui.ApplicationModel.Platform.AppContext, Drawable.scrollview_thumb);
    handler.PlatformView.ScrollbarFadingEnabled = false;
    handler.PlatformView.ScrollBarSize = 20;
#endif
});
```

By setting `VerticalScrollBarEnabled` to true and specifying a custom drawable for the `VerticalScrollbarThumbDrawable`, the vertical scrollbar will always be visible on Android devices.

## See Also

- [Customizing Appearance](https://docs.microsoft.com/en-us/dotnet/maui/user-interface/styles/)
- [MAUI Handlers Architecture](https://docs.microsoft.com/en-us/dotnet/maui/fundamentals/handlers/)
