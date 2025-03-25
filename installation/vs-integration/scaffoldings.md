---
title: Scaffolding Pages and Screens
page_title: Telerik UI for .NET MAUI Scaffoldings - Visual Studio Scaffoldings
description: Learn how to add predefined screens in your application using via Telerik .NET MAUI Visual Studio Scaffoldings.
slug: maui-vs-scaffoldings
position: 10
tags: maui, dotnet maui, item templates, scaffoldings, predefined pages, screens, visual studio
previous_url: /installation/windows/scaffoldings
---

# .NET MAUI Scaffolding Pages and Screens for Visual Studio

The Telerik UI for .NET MAUI Visual Studio extension lets you scaffold an app page (screen) and increase your productivity. The scaffoldings allow you to quickly add predefined pages with controls to your application and define the parameters of the controls through an UI.

## Get the Extension

To use the Telerik UI for .NET MAUI Scaffoldings, install the `Progress Telerik UI for .NET MAUI Extension` for Visual Studio. You can get the extension from:

* <a href="https://marketplace.visualstudio.com/items?itemName=TelerikInc.ProgressTelerikMAUIExtensions" target="_blank">The Visual Studio Marketplace.</a>

* The Extensions tab in Visual Studio&mdash;search for `Progress Telerik UI for .NET MAUI Extension`, select the extension, and then click **Install**.

* The Telerik UI for .NET MAUI [MSI installer]({%slug automated-installer %}). 

For more information, go to the [Productivity Extensions for Visual Studio]({% slug vs-integration-overview %}) topic.

## Add The Scaffolding Page to Your App

To add the desired screen to your MAUI application:

1. Open the project in Visual Studio.
1. Right-click the name of the project.
1. From the popup menu select **Telerik UI for .NET MAUI** -> **Add new Scaffolded Item**.
![.NET MAUI Scaffolding dialog](images/scaffolding-vs-dialog.png)

1. From the UI form, select the desired page and set the available parameters.
![.NET MAUI Scaffolding options](images/scaffolding-vs-options.png)

As a result, the VS code extension does the following:
* Adds the page to the `Pages` folder of the application. If the folder does not exist, it will be created. 
* Adds a `ViewModel` for the created page to the `ViewModels` folder. If the folder does not exist, it will be created.

The next image shows the file structure created for the `DataGrid` page:
![.NET MAUI Scaffolding result](images/scaffolding-vs-result.png)

## Displaying a Scaffolded Screen in Your App

To show a newly scaffolded page in your MAUI app, specify the page's namespace.

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
        ContentTemplate="{DataTemplate pages:TelerikDataGridPage}"
        Route="MainPage" />

</Shell>
```

This is the result on Android and WinUI:

![.NET MAUI Scaffolding screen look](../images/datagrid_page.png)

## Theme Aware

The Scaffolding page templates use the [Telerik .NET MAUI controls](https://www.telerik.com/maui-ui).
To control the visual appearance of the controls in the pages when changing the theme on device or app level, apply [Telerik theming]({%slug themes-overview%}) to the project. 
You can set various [theme swatches]({%slug themes-overview%}#swatch) in the application and change them at runtime based on the applied device theme.

or more details on the suggested implementation, see the [Changing the Theme at Runtime KB article]({%slug change-telerik-theme-runtime%}).

## Available Scaffoldings

* [CollectionView page](#products-page)
* [DataGrid page](#datagrid-page)
* [Login page](#login-screen)
* [Register page](#register-screen)
* [Reset password page](#reset-password-screen)

### CollectionView Page

The CollectionView page represents a list of products. The main control used on this page is the Telerik UI for .NET MAUI [CollectionView]({%slug collectionview-overview%}) control. The scaffolding page allows you to configure the selection mode of the CollectionView and whether to add the predefined icons used in the template.

The image shows the default appearance of the page:

![.NET MAUI Products Page](../images/products_page.png)

### DataGrid Page

The DataGrid page represents a data displayed in a table. The main control used on this page is the Telerik UI for .NET MAUI [DataGrid]({%slug datagrid-overview%}) control. The scaffolding page allows you to configure the data source used in the DataGrid, the selection mode, whether editing, sorting, filtering and grouping the data in the control will be enabled.

The image shows the default appearance of the page:

![.NET MAUI DataGrid Page](../images/datagrid_page.png)

### Login Page

The Login screen represents a login panel. The main controls used on this screen are the Telerik UI for .NET MAUI [Entry]({%slug entry-overview%}) and [TemplatedButton]({%slug templatedbutton-overview%}) controls. The scaffolding page allows you to add a social login panel to this screen.

The image shows the default appearance of the page:

![.NET MAUI Login Page](../images/login_screen.png)

### Register Page

The Register page allows you to add a register page to your .NET MAUI application. The main controls used on this screen are the Telerik UI for .NET MAUI [Entry]({%slug entry-overview%}) and [TemplatedButton]({%slug templatedbutton-overview%}) controls.

The image shows the default appearance of the page:

![.NET MAUI Register Page](../images/register_screen.png)

### Reset Password Page

The Reset Password page allows you to add a reset password page to your application. The main controls used on this screen are the Telerik UI for .NET MAUI [Entry]({%slug entry-overview%}) and [TemplatedButton]({%slug templatedbutton-overview%}) controls.

The image shows the default appearance of the page:

![.NET MAUI Reset Password Page](../images/reset_screen.png)

## See Also

* [UI for MAUI Installation Methods]({%slug installation-approaches%})
* [System Requirements for Windows]({% slug system-requirements %})
* [Productivity Extensions for Visual Studio]({% slug vs-integration-overview %})
* [Telerik UI for .NET MAUI Sample Apps]({% slug controls-samples-app %})