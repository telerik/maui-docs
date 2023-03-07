---
title: Toolbox VS Extension
page_title: Telerik Toolbox VS Extension for .NET MAUI on Windows
description: Learn more about the Telerik Toolbox extension for .NET MAUI on Windows and how to use the toolbox with the Telerik UI for .NET MAUI library.
slug: toolbox-support
position: 3
previous_url: /installation/windows/toolbox-support
---

# Telerik Toolbox for .NET MAUI on Windows

Telerik products support the Toolbox extension for Visual Studio (VS) on Windows. The Toolbox is part of the Visual Studio extensions for Telerik UI for .NET MAUI and facilitates the process of adding Telerik controls to your .NET MAUI application.

The Telerik UI for .NET MAUI VS extensions are distributed with the Telerik UI for .NET MAUI [MSI installation]({%slug maui-getting-started%}). You can also download and install them as a separate product from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/) for Visual Studio 2022.

> For more information, go to the topic about [getting started with the Telerik VS extensions]({%slug visualstudio-extensions%}) topic.

## Adding Controls with the Toolbox

To add the desired Telerik UI for .NET MAUI controls with the Toolbox:

1. In Visual Studio, navigate to the **Extensions** tab.
1. Select **Telerik** > **Telerik UI for .NET MAUI** > **Open Telerik UI for .NET MAUI Toolbox**.

  Alternatively, in the top right corner in Visual Studio for Windows, find the **Quick Launch** search field and type **Telerik UI for .NET MAUI Toolbox**.

  ![VS Extensions dialog with the path of selected options showing the Open Telerik UI for .NET MAUI Toolbox](images/enabled_toolbox.png)

1. Open the Toolbox. As a result, a window with the controls from the suite will appear.

  >important If the controls you see in the Toolbox are not the ones you need, make sure that you've added all the required references. Then, rebuild your project.

1. To embed the controls, drag one of them within your XAML file. As a result, the control definition will be added to your project and the needed namespace declarations will be mapped.

  ![Adding Telerik .NET MAUI controls from the Toolbox by dragging and dropping](images/maui_toolbox.gif)

## See Also

- [Installing VSExtensions]({%slug visualstudio-extensions%})
- [MSI installation]({%slug maui-getting-started%})
