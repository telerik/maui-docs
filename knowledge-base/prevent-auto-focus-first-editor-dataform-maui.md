---
title: Preventing Auto-Focus on the First Editor in ScrollView in MAUI
description: Learn how to stop the first editor from automatically gaining focus in a ScrollView within the DataForm component for MAUI on WinUI.
type: troubleshooting
page_title: How to Prevent First Editor Auto-Focus in ScrollView for MAUI DataForm
slug: prevent-auto-focus-first-editor-dataform-maui
tags: dataform, maui, scrollview, autofocus, editor
res_type: kb
---

## Environment

| Control | Author | 
| ---- | ---- | 
| Input Editors in a ScrollView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

When using the DataForm component for .NET MAUI with multiple input controls inside a ScrollView, the first editor automatically gains focus after tapping outside any input control. This behavior is observed specifically on the WinUI platform. For instance, in the default RadDataForm, its `ControlTemplate` wraps the `ContentPresenter` in a ScrollView, causing the first DataForm Editor (if it's a RadEntryEditor, etc.) to auto-focus erroneously upon an external tap.

## Cause

This issue arises due to a known WinUI behavior where the first `Entry` in a `ScrollView` gains focus automatically when users interact with the application outside of the input controls. This can disrupt the expected user experience in applications where multiple inputs are present, and not all interactions are meant to refocus the first editor.

## Solution

To resolve this issue and prevent the first editor from automatically gaining focus inside a ScrollView, you can use a handler mapping for the ScrollView. This solution involves modifying the `ScrollViewHandler` to adjust its focus behavior specifically for the WinUI platform.

Add the following code snippet inside the `App.xaml.cs` file of your MAUI project:

```C#
using Microsoft.Maui.Handlers;
using Microsoft.Maui.Platform;

public partial class App : Application
{
    public App()
    {
#if WINDOWS
        ScrollViewHandler.Mapper.AppendToMapping(nameof(IScrollView.Content), MapContent);
#endif

        InitializeComponent();

        MainPage = new AppShell();
    }

#if WINDOWS
    private static void MapContent(IScrollViewHandler handler, IScrollView view)
    {
        if (handler.PlatformView == null || handler.MauiContext == null
            || view.PresentedContent == null || handler.PlatformView.Content is not ContentPanel)
        {
            return;
        }

        var panel = (ContentPanel)handler.PlatformView.Content;
        panel.IsTabStop = true;
    }
#endif
}
```

This code snippet adjusts the focus behavior for ScrollView on the WinUI platform by setting the `IsTabStop` property of the `ContentPanel` to `true`. This change ensures that the first editor within a ScrollView does not automatically gain focus when users tap outside of it, providing a more intuitive user experience.

## See Also

- [ScrollView in .NET MAUI](https://docs.microsoft.com/en-us/dotnet/maui/user-interface/layouts/scrollview)
