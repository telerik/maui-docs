---
title: Scaffolding Pages and Screens
page_title: Telerik UI for .NET MAUI Code Scaffoldings - Visual Studio Code Scaffoldings
description: Learn how to add predefined screens in your application using the Telerik .NET MAUI Visual Studio Code Scaffoldings.
slug: maui-vs-code-scaffoldings
position: 5
tags: maui, dotnet maui, item templates, scaffoldings, predefined pages, screens, visual studio code
---

# Scaffolding Pages and Screens for Visual Studio Code

The Telerik UI for .NET MAUI Visual Studio Code extension lets you scaffold an app page (screen) and increase your productivity. The scaffoldings allow you to quickly add predefined pages with controls to your application and define the parameters of the controls through an UI.

## Get the Extension

To use the Telerik UI for .NET MAUI Scaffoldings, install the `Telerik UI for .NET MAUI Productivity Tools` extension for Visual Studio Code. You can get the extension from:

* <a href="https://marketplace.visualstudio.com/items?itemName=TelerikInc.telerik-maui-productivity-tools" target="_blank">The Visual Studio Code Marketplace.</a>

* The **Extensions** tab in Visual Studio Code&mdash;search for `Telerik UI for .NET MAUI Productivity Tools`, select the extension, and then click **Install**.

## Add The Scaffolding Page to Your App

To add the desired screen to your MAUI application:

1. Open the project in Visual Studio Code.
1. Right-click the name of the `.csproj` file.

1. From the popup menu, select **New Telerik UI for .NET MAUI Project Item Generator**.
![.NET MAUI Scaffolding dialog](images/scaffolding-vscode-dialog.png)

1. From the UI form, select the desired page and set the available parameters.
![.NET MAUI Scaffolding dialog](images/scaffolding-vscode-options.png)

As a result, the VS code extension does the following:
* Adds the page to the `Pages` folder of the application. If the folder does not exist, it will be created. 
* Adds a `ViewModel` for the created page to the `ViewModels` folder. If the folder does not exist, it will be created.

The next image shows the file structure created for the `DataGrid` page:
![.NET MAUI Scaffolding result](images/scaffolding-vscode-result.png)

## Displaying a Scaffolded Screen in Your App

To show a newly scaffolded page in your MAUI app, specify the page's namespace.

### Using a Blank App Template

Set the screen directly to the `MainPage` of the application isndie the `App.xaml.cs` file when using a Blank app template 

```C#
MainPage = new MyApp.Pages.TelerikDataGridPage();
```

### Using a Blank Shell App Template

Set the screen directly to the `ShellContent` inside the `AppShell.xaml` file when using a Blank Shell app.

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
        ContentTemplate="{DataTemplate pages:TelerikCollectionViewPage}"
        Route="MainPage" />

</Shell>
```

This is the result on iOS and MacCatalyst:

![.NET MAUI Scaffolding screen look](images/scaffolding-vscode-screen-look.png)

## Available Scaffoldings

* [Products page](#products-page)
* [DataGrid page](#datagrid-page)
* [Login screen](#login-screen)
* [Register screen](#register-screen)
* [Reset password screen](#reset-password-screen)

### Products Page

The Products page represents a list of products. The main control used on this page is the Telerik UI for .NET MAUI [CollectionView]({%slug collectionview-overview%}) control. The scaffolding page allows you to configure the selection mode of the CollectionView and whether to add the predefined icons used in the template.

The image shows the default appearance of the page:

![.NET MAUI Products Page](../images/products_page.png)

### DataGrid Page

The DataGrid page represents a data displayed in a table. The main control used on this page is the Telerik UI for .NET MAUI [DataGrid]({%slug datagrid-overview%}) control. The scaffolding page allows you to configure the data source used in the DataGrid, the selection mode, whether editing, sorting, filtering and grouping the data in the control will be enabled.

The image shows the default appearance of the page:

![.NET MAUI DataGrid Page](../images/datagrid_page.png)

### Login Screen

The Login screen represents a login panel. The main controls used on this screen are the Telerik UI for .NET MAUI [Entry]({%slug entry-overview%}) and [TemplatedButton]({%slug templatedbutton-overview%}) controls. The scaffolding page allows you to add a social login panel to this screen.

The image shows the default appearance of the page:

![.NET MAUI Login Screen](../images/login_screen.png)

### Register Screen

This screen allows you to add a register page to your .NET MAUI application. The main controls used on this screen are the Telerik UI for .NET MAUI [Entry]({%slug entry-overview%}) and [TemplatedButton]({%slug templatedbutton-overview%}) controls.

The image shows the default appearance of the page:

![.NET MAUI Register Screen](../images/register_screen.png)

### Reset Password Screen

This screen allows you to add a reset password page to your application. The main controls used on this screen are the Telerik UI for .NET MAUI [Entry]({%slug entry-overview%}) and [TemplatedButton]({%slug templatedbutton-overview%}) controls.

The image shows the default appearance of the page:

![.NET MAUI Reset Password Screen](../images/reset_screen.png)



