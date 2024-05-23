---
title: Font Icons
page_title: .NET MAUI Font Icons - Overview
description: Telerik font icons are collections of small vector graphics used across the components in the Telerik UI for .NET MAUI suite.
slug: telerik-font-icons
position: 0
---

# Telerik UI for .NET MAUI Font Icons

Telerik font icons represents collection of small vector graphics used across the components from Telerik UI for .NET MAUI suite. Examples of using font icons include the expand and collapse indicators of Accordion, Expander and TreeView controls, filter and sort indicators of DataGrid control, and other.

This article will give an overview on how you can utilize the Telerik font icons in your .NET MAUI app. 

## Include the Required Telerik Font File

1. The Telerik Font Icons are located in the `telerikcontrolsicons.ttf` and `telerikfontexamples.ttf` files. There are two options you could use to get the `.ttf` file.

	* Download the `.ttf` files from <a href="https://github.com/telerik/maui-samples/tree/main/Samples/ControlsSamples/Resources/Fonts" target="_blank">Telerik UI for .NET MAUI Samples App GitHub repo</a>.
	* Get the font file from the installation folder of Telerik UI for MAUI - here is the path to the exact location: `Telerik UI for .NET MAUI [version]\Examples\ControlsSamples\Resources\Fonts`

2. Add the font to your project by placing it in the `Resources/Fonts` folder.

3. Register the Telerik Font `.ttf` file into your .NET MAUI application inside the `MauiProgram.cs` file:

```C#
.ConfigureFonts(fonts =>
{
    fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
    fonts.AddFont("OpenSans-Semibold.ttf", "OpenSansSemibold");
    fonts.AddFont("telerikcontrolsicons.ttf", "TelerikControlsIcons");
    fonts.AddFont("telerikfontexamples.ttf", "TelerikFontExamples");
});
```

## Available Icons

* [List with Telerik Examples Icons]({%slug telerik-examples-icons%})

* [List with Telerik Controls Icons]({%slug telerik-controls-icons%})

## See Also

[Telerik Examples Icons]({%slug telerik-examples-icons%})
[Telerik Controls Icons]({%slug telerik-controls-icons%})