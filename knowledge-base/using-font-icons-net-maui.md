---
title: Using Font Icons in Telerik UI for .NET MAUI
description: Learn how to use font icons in Telerik UI for .NET MAUI and find the complete list of available icons.
type: how-to
page_title: Using Font Icons in Telerik UI for .NET MAUI
slug: using-font-icons-net-maui
tags: font-icons, .NET MAUI, Telerik, how-to
res_type: kb
---

# Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | Telerik UI for .NET MAUI Font Icons | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

# Description

I would like to know how to use font icons in Telerik UI for .NET MAUI. Additionally, I am interested in finding the complete list of available font icons.

# Solution

To use font icons in your Telerik UI for .NET MAUI application, follow these steps:

1. Download the [font file](https://github.com/telerik/maui-samples/blob/main/Samples/SdkBrowser/Resources/Fonts/telerikfontexamples.ttf).

2. Add the font to your project by placing it in the `Resources/Fonts` folder.

3. Register the font in the `MauiProgram.cs` file:

```csharp
.ConfigureFonts(fonts =>
{
    fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
    fonts.AddFont("OpenSans-Semibold.ttf", "OpenSansSemibold");
    fonts.AddFont("telerikfontexamples.ttf", "TelerikFontExamples");
});
```

4. Consume the font icon in your XAML:

```xaml
<Label Text="&#xE80A;" FontFamily="TelerikFontExamples" FontSize="Micro" FontAttributes="Bold" TextColor="Black" />
```

To find the complete list of available font icons, you can use an extension such as the [iconfont-preview extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=stxr.iconfont-preview).


# See Also

- [Using Telerik Font Icons in Xamarin](https://docs.telerik.com/devtools/xamarin/styling-and-appearance/telerik-font-icons)
