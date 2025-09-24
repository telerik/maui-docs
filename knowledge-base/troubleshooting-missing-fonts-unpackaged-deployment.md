---
title: Troubleshooting Missing Fonts in Unpackaged Deployment
description: This article provides troubleshooting steps for resolving the issue of missing fonts in an unpackaged deployment of a .NET MAUI app.
type: troubleshooting
page_title: Troubleshooting Missing Fonts in Unpackaged Deployment | Telerik UI for .NET MAUI
slug: troubleshooting-missing-fonts-unpackaged-deployment
tags: troubleshooting, fonts, unpackaged deployment, .NET MAUI
res_type: kb
---
## Environment

| Product | Version |
| ------- | ------- |
| Progress® Telerik® UI for .NET MAUI | 6.5.0 |

## Description
I am experiencing an issue with missing fonts in an unpackaged deployment of my .NET MAUI app. When I publish the app as an exe, the fonts are not loaded. I have followed the documentation and tried different approaches, but the issue persists.

## Solution
To resolve the issue of missing fonts in an unpackaged deployment of a .NET MAUI app, follow these steps:

1. Add the font files used in your app to the `Resources/Fonts` folder of your project.
2. Right-click on each font file and set the **Build Action** property to **Copy Always**.
3. Update the `MauiProgram.cs` file and register the font files by adding the following code:

```csharp
.ConfigureFonts(fonts =>
{
    fonts.AddFont("font1.ttf", "Font1");
    fonts.AddFont("font2.ttf", "Font2");
    // Add more font files if necessary
});
```
Make sure to replace "font1.ttf" and "Font1" with the actual file name and font family name of your font files.

4. Build and run the app to verify if the fonts are loading correctly in the unpackaged deployment.

If the issue persists, check the following:

- Double-check the spelling and case sensitivity of the font file and font family names.
- Test the app on both Windows 10 and Windows Server 2019 to rule out any platform-specific issues.

### Additional Approach

If you are still having trouble after ensuring the registration and the case-sensitive spelling is correct, there is another thing you can add to your approach. Hook into the LabelHandler's Mapper and change the native Windows font family property dynamically:

```csharp
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
            fonts.AddFont("telerikfontexamples.ttf", "telerikfontexamples");
            fonts.AddFont("telerikcontrolsicons.ttf", "telerikfontexamples");
        });

#if WINDOWS10_0_17763_0_OR_GREATER
    Microsoft.Maui.Handlers.LabelHandler.Mapper.AppendToMapping("FontFamily", (handler, element) =>
    {
        /*  An unpackaged app does not have ms-appx://Assets/ folder available. To avoid issues you can explicitly define the new path to the font file
         *
         *  - Packaged => "ms-appx://Assets/Fonts/Font.ttf#familyname" 
         *  - Unpackaged => "font.ttf#familyname"
         *
         *  In order for the unpackaged approach to work, be sure to include the font's file with the project's assets and set the Build Action to 'CopyAlways'
        */

        handler.PlatformView.FontFamily = element.Font.Family.ToLower() switch
        {
            "telerikcontrolsicons" => new Microsoft.UI.Xaml.Media.FontFamily("telerikcontrolsicons.ttf#telerikcontrolsicons"),
            "telerikfontexamples" => new Microsoft.UI.Xaml.Media.FontFamily("telerikfontexamples.ttf#telerikfontexamples"),
            _ => handler.PlatformView.FontFamily
        };
    });
#endif

    return builder.Build();
}
```

Note: If you are looking for the font files used in the previous code example, you can find them in the [Telerik UI for Maui Samples](https://github.com/telerik/maui-samples/tree/main/Samples/ControlsSamples/Resources/Fonts) source code. This prpblem is not specific to Telerik fonts, it can happen with any font that is not available by default. 

### Further Assistance

If the issue still persists after following these steps, please provide a reproducible project and reach out to the Microsoft MAUI team for further investigation. You can get assistance in two locations:

- [.NET MAUI on GitHub](https://github.com/dotnet/maui/issues) (always search open Issues before creating a new Issue
- [Microsoft Q&A for .NET MAUI](https://learn.microsoft.com/en-us/answers/tags/247/dotnet-maui)

## Notes
- Make sure to use the correct spelling and case sensitivity when registering the font files in the `MauiProgram.cs` file.
- Test the app on both Windows 10 and Windows Server 2019 to ensure compatibility.
- Stay updated with the latest versions of Telerik UI for .NET MAUI and the Microsoft MAUI framework to benefit from any bug fixes or improvements.
- Refer to the official Microsoft MAUI documentation for more information on working with custom fonts in .NET MAUI.

## See Also
- [Microsoft MAUI Documentation - Working with Fonts](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/fonts?view=net-maui-8.0)
