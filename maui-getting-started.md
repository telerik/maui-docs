---
title: Getting Started
page_title: Getting Started with Telerik .NET MAUI controls
description: Getting Started with .NET MAUI - Telerik UI controls for .NET MAUI
slug: maui-getting-started
tags: .net maui, ui for .net maui, .net maui controls
position: 1
---

# Getting Started

This article will guide you through the basics of Telerik UI for MAUI and how to start using the product.

## Getting Started with .NET MAUI

Information about what are the exact steps to get started with Microsoft .NET MAUI and what are the system requrements are desricbed inside the [Microsoft .NET MAUI GitHub repo Wiki page](https://github.com/dotnet/maui/wiki/Getting-Started)

## Getting Started with Telerik .NET MAUI

Once you have .NET MAUI configured on your machine, then follow the steps needed to set up the Telerik UI for .NET MAUI. 

>important Telerik .NET MAUI Preview controls are available for Android and iOS

### Download product files

**1. Log into your [Telerik account](https://www.telerik.com/account/).**

**2. Go to [Telerik UI for MAUI product page](https://www.telerik.com/maui-ui)**

**3. Click Download Telerik UI for MAUI button:**

![Telerik UI for .NET MAUI](images/download_maui.png)

**4. The download starts automatically**

![Telerik UI for .NET MAUI](images/downloading-maui.png)

### Installation for Windows

* Telerik_UI_for_Maui_[version]_Preview.msi - runnable msi file used for automatic installation (for use on PC). Run the MSI file and follow the instructions. On a 32bit machine the wizard will install the UI for MAUI component in the following folder unless you specify otherwise: C:\Program Files\Progress\ or C:\Program Files (x86)\Progress\ for a 64bit machine.

The installation folder has the following subdirectories:

![Telerik UI for MAUI Installation Folder](images/telerik-ui-for-maui-installation-folder.png)

* Binaries - Contains the needed dlls for Android and iOS 
* DemoApp - Dempo App with Telerik UI for .NET MAUI controls
* LicenseAgreements - provides the product EULA.
* Packages - Telerik_UI_for_Maui_[version]_Preview.nupkg file

### Installation for macOS

* Telerik_UI_for_Maui_[version]_Preview.pkg - runnable pkg file used for automatic installation (for use on Mac).

The installation folder has the following subdirectories:

![Telerik UI for MAUI Installation Folder](images/installation-macos.png)

* Binaries - Contains the needed dlls for Android and iOS 
* DemoApp - Dempo App with Telerik UI for .NET MAUI controls
* LicenseAgreements - provides the product EULA.
* Packages - Telerik_UI_for_Maui_[version]_Preview.nupkg file

### NuGet Package

* Telerik_UI_for_Maui_[version]_Preview.nupkg file for Windows and macOS users.

## Register the needed handlers and renderers

In order to visualize the Telerik UI for MAUI controls you have to register the needed renderers for Button, Chart and ListView controls inside the `ConfigureMauiHandlers` method of the **Startup.cs** file of your project. 

Here is how the Startup.cs file looks when Telerik UI for .NET MAUI renderers are registered.

```C#
public class Startup : IStartup
{
    public void Configure(IAppHostBuilder appBuilder)
    {
        appBuilder
            .UseFormsCompatibility()
            .ConfigureFonts(fonts => {
                fonts.AddFont("ionicons.ttf", "IonIcons");
            })
            .ConfigureMauiHandlers(handlers => {
                // ****** Compatibility Renderers ***** //
				
                // Compatibillity renderer for Telerik UI for MAUI Button control
                handlers.AddCompatibilityRenderer(typeof(Telerik.XamarinForms.Input.RadButton), typeof(InputRenderer.ButtonRenderer));

                // Compatibillity renderer for Telerik UI for MAUI RadCartesianChart control
                handlers.AddCompatibilityRenderer(typeof(Telerik.XamarinForms.Chart.RadCartesianChart), typeof(ChartRenderer.CartesianChartRenderer));

                // Compatibillity renderer for Telerik UI for MAUI RadPieChart control
                handlers.AddCompatibilityRenderer(typeof(Telerik.XamarinForms.Chart.RadPieChart), typeof(ChartRenderer.PieChartRenderer));

                // Compatibillity renderer for Telerik UI for MAUI RadListView control
                handlers.AddCompatibilityRenderer(typeof(Telerik.XamarinForms.DataControls.RadListView), typeof(DataControlsRenderer.ListViewRenderer));
                                                
                // ****** Handlers ***** //       
				                        
                // Add the Telerik UI for MAUI Handlers for ItemsControl control
                handlers.AddHandler<IRadItemsControl, RadItemsControlHandler>();
                                                
                // Add the handlers for Telerik UI for MAUI Border control
                handlers.AddHandler<IRadBorder, RadBorderHandler>();
            })
            .UseMauiApp<App>()
            .ConfigureLifecycleEvents(lifecycle => {
#if ANDROID
                lifecycle.AddAndroid(d => {
                    d.OnBackPressed(activity => {
                        System.Diagnostics.Debug.WriteLine("Back button pressed!");
                    });
                });
#endif
            });
    }
}
```

## Demo App

Telerik UI for MAUI.Preview version comes with a sample app, which demonstrates the Telerik Preview controls for Microsoft .NET MAUI. For more details visit our [Demo App article]({%slug maui-demo-app%}).

### Telerik UI for MAUI Demo App on Android

![Telerik UI for .NET MAUI Demo Application Folder](images/demo.png)

### Telerik UI for MAUI Demo App on iPad

![Telerik UI for .NET MAUI Demo Application Folder](images/demo-ipad.png)

## See Also

* [Border]({%slug border-overview%})
* [Button]({%slug button-overview%})
* [Chart]({%slug chart-overview%})
* [ItemsControl]({%slug itemscontrol-overview%})
