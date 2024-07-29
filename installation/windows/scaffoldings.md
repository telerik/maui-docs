---
title: Telerik UI for .NET MAUI Scaffoldings
page_title: Telerik UI for .NET MAUI Scaffoldings - Visual Studio Scaffoldings
description: Learn how to add predefined screens in your application using via Telerik .NET MAUI Visual Studio Scaffoldings.
slug: maui-vs-scaffoldings
position: 10
tags: maui, dotnet maui, item templates, scaffoldings, predefined pages, screens, visual studio
---

# .NET MAUI Scaffoldings for Visual Studio

The Telerik UI for .NET MAUI Visual Studio extension provides scaffoldings for increased developer productivity. The scaffoldings allow you to quickly add predefined pages with controls to your application and define the parameters of the controls through an UI.

## Get the Extension

To use the Telerik UI for .NET MAUI Scaffoldings, install the `Progress Telerik UI for .NET MAUI Extension` extension for Visual Studio. You can get the extension from:

* <a href="https://marketplace.visualstudio.com/items?itemName=TelerikInc.ProgressTelerikMAUIExtensions" target="_blank">The Visual Studio Marketplace.</a>

* The Extensions tab in Visual Studio  - search for `Progress Telerik UI for .NET MAUI Extension`, select the extension, and then click `Install`.

* The Telerik UI for .NET MAUI [MSI installation]({%slug maui-getting-started%}). For more information, go to the [getting started with the Telerik VS extensions]({%slug visualstudio-extensions%}) topic.

## Add The Scaffolding Page to Your App

Here are the steps you need to follow to add the desired screen to your application:

1. Open the project in Visual Studio.
1. Right-click on the name of the project.
1. From the popup menu select `Telerik UI for .NET MAUI` -> `Add new Scaffolded Item`.
![.NET MAUI Scaffolding dialog](images/scaffolding-vs-dialog.png)

1. From the UI form, select the desired page and set the available parameters.
![.NET MAUI Scaffolding options](images/scaffolding-vs-options.png)

1. The page will be added to the `Pages` folder of the application. if one does not exist, it will be created. Every page has a `ViewModel`, so the `ViewModel` is added to the `ViewModels` folder. if one does not exist, it will be created. The image shows the `Products` screen after adding to the project.
![.NET MAUI Scaffolding result](images/scaffolding-vs-result.png)

1. To display the screen in your application you need to specify the page namespace.

In the example below, the screen is set directly to the `ShellContent` in the `AppShell.xaml`:

```XAML
<Shell
    x:Class="TestScaffoldings.AppShell"
    xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:local="clr-namespace:TestScaffoldings"
    xmlns:pages="clr-namespace:MyApp.Pages"
    Shell.FlyoutBehavior="Disabled"
    Title="TestScaffoldings">

    <ShellContent
        Title="Home"
        ContentTemplate="{DataTemplate pages:TelerikProductsListPage}"
        Route="MainPage" />

</Shell>
```

This is the result on Android and WinUI:

![.NET MAUI Scaffolding screen look](images/scaffolding-vs-screen-look.png)

## Available Scaffoldings

* Products page&mdash;Uses the Telerik UI for .NET MAUI [CollectionView]({%slug collectionview-overview%}) control.
* DataGrid page&mdash;Uses the Telerik UI for .NET MAUI [DataGrid]({%slug datagrid-overview%}) control.
* Login page&mdash;Uses the Telerik UI for .NET MAUI [Entry]({%slug entry-overview%}) and [TemplatedButton]({%slug templatedbutton-overview%}) controls.
* Register page&mdash;Uses the Telerik UI for .NET MAUI [Entry]({%slug entry-overview%}) and [TemplatedButton]({%slug templatedbutton-overview%}) controls.
* Reset password page&mdash;Uses the Telerik UI for .NET MAUI [Entry]({%slug entry-overview%}) and [TemplatedButton]({%slug templatedbutton-overview%}) controls.

## See Also

* [Available Product Files and Assemblies]({% slug download-product-files %})
* [System Requirements for Windows]({% slug system-requirements %})
* [Telerik Extensions and Project Templates for VS on Windows]({% slug visualstudio-extensions %})
* [Telerik UI for .NET MAUI Sample Apps]({% slug controls-samples-app %})