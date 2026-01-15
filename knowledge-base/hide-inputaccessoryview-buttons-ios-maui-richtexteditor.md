---
title: Hiding InputAccessoryView Buttons on iOS for Telerik MAUI RichTextEditor
description: Learn how to hide the InputAccessoryView buttons on iOS when using Telerik MAUI RichTextEditor.
type: how-to
page_title: Remove Toolbar Buttons from Keyboard on iOS in Telerik MAUI RichTextEditor
meta_title: Remove Toolbar Buttons from Keyboard on iOS in Telerik MAUI RichTextEditor
slug: hide-inputaccessoryview-buttons-ios-maui-richtexteditor
tags: maui, richtexteditor, ios, inputaccessoryview, webviewhandler, toolbar
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 12.0.0 | Telerik UI for .NET MAUI RichTextEditor | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to hide the `InputAccessoryView` buttons that appear on the keyboard toolbar when using the Telerik [UI for .NET MAUI RichTextEditor](https://www.telerik.com/maui-ui/documentation/controls/richtexteditor/overview) control on iOS. This is required because the RichTextEditor internally uses the MAUI WebView, and the toolbar buttons are part of the WebView's native configuration.

This knowledge base article also answers the following questions:
- How to remove toolbar buttons from the iOS keyboard in Telerik MAUI RichTextEditor?
- How to customize `InputAccessoryView` in MAUI WebView for Telerik RichTextEditor?
- How to disable `UIToolbar` buttons for WebView in Telerik MAUI RichTextEditor?

## Solution

To hide the `InputAccessoryView` buttons on iOS, add custom logic for the WebView inside the `MauiProgram.cs` file. Follow these steps:

1. Open the `MauiProgram.cs` file in your project.
2. Add the following code snippet to customize the WebViewHandler:

```csharp
public static class MauiProgram
{
    public static MauiApp CreateMauiApp()
    {
        var builder = MauiApp.CreateBuilder();
        builder
            .UseMauiApp<App>()
            .UseTelerik()
            .ConfigureFonts(fonts =>
            {
                fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
                fonts.AddFont("OpenSans-Semibold.ttf", "OpenSansSemibold");
            });
#if IOS
        Microsoft.Maui.Handlers.WebViewHandler.Mapper.AppendToMapping("MyCustomization", (handler, view) => 
        {
            var myView = handler.PlatformView;
            var item = myView.InputAssistantItem;
            if (item != null)
            {
                item.LeadingBarButtonGroups = System.Array.Empty<UIKit.UIBarButtonItemGroup>();
                item.TrailingBarButtonGroups = System.Array.Empty<UIKit.UIBarButtonItemGroup>();
            }
        });
#endif
        return builder.Build();
    }
}
```

## See Also

- [UI for .NET MAUI RichTextEditor Documentation](https://www.telerik.com/maui-ui/documentation/controls/richtexteditor/overview)
- [WebView Control in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/webview)
