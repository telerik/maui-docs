---
title: Toolbox Extension for VS
page_title: Telerik Toolbox VS Extension for .NET MAUI on macOS
description: Learn more about the Telerik Toolbox extension for .NET MAUI on macOS and how to use the toolbox with the Telerik UI for .NET MAUI library.
slug: toolbox-support-mac
position: 3
previous_url: /installation/mac/toolbox-extension-mac
---

# Telerik Toolbox for .NET MAUI on macOS

The Telerik .NET MAUI product has a support for Toolbox extension in Visual Studio (VS) on macOS. The Toolbox facilitates the process of adding Telerik controls to your .NET MAUI application.

>important Telerik Visual Studio Toolbox extension for Mac will be phased out in 2024, following the [discontinuation of Visual Studio for Mac](https://devblogs.microsoft.com/visualstudio/visual-studio-for-mac-retirement-announcement/). As a recommended replacement, consider using the [.NET MAUI Extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.dotnet-maui) for Visual Studio Code. For detailed guidance on getting started with the .NET MAUI Extension for Visual Studio Code, refer to our [blog post](https://www.telerik.com/blogs/beyond-basics-getting-started-net-maui-extension-visual-studio-code).

## Adding Controls with the Toolbox

1. Install the [Project Template for VS for macOS]({%slug mac-project-template %}).
1. In your project, navigate to the `MainPage.xaml` file.
1. Click `MainPage.xaml` or any other XAML file inside your project. As a result, and if the `telerik.ui.for.maui.mpack` file has been successfully installed, you will be able to see the **Toolbox** window.

  ![Showing the Telerik Toolbox when clicking on the MainPage.xaml file](images/enabled_toolbox_mac.png)

  Alternatively, in the top right corner in Visual Studio for macOS, find the **Search** field and type **Toolbox**.

  ![Showing the Telerik Toolbox from the Search field](images/search_toolbox_mac.png)

1. Click the **Toolbox** option. As a result, you will be prompted to the window which contains the controls from the suite.

  >important If the controls you see in the Toolbox are not the ones you need, make sure that you've added all the required references. Then, rebuild your project.

1. To embed the controls, drag one of them within your XAML file. As a result, the control definition will be added to your project and the needed namespace declarations will be mapped.

  ![Adding Telerik .NET MAUI controls from the Toolbox by dragging and dropping on macOS](images/toolbox_mac.gif)

## See Also

* [Available Product Files and Assemblies]({% slug download-product-files %})
* [System Requirements for macOS]({% slug system-requirements-mac %})
* [Telerik Project Template for VS on macOS]({% slug mac-project-template %})
* [Telerik UI for .NET MAUI Sample Apps]({% slug sampleapps-overview %})
