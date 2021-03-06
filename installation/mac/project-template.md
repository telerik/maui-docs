---
title: Project Template for Visual Studio for Mac
page_title: Project Template for Visual Studio for Mac
description: All you need to know about the project template for Visual Studio on Mac. Find all you need to know in .NET MAUI installation documentation.
slug: mac-project-template
position: 1
---

# Project Template for Visual Studio for Mac

The Telerik UI for .NET MAUI project template is a Visual Studio add-in that improves the getting started experience for Telerik customers. It provides a project template that is pre-setup with all requirements to run our components, so you can start writing .NET MAUI apps right away.

## Installation

You can access the Telerik UI for .NET MAUI Project Template in the following ways:

* If you have already installed Telerik UI for .NET MAUI, navigate to the **/[installation-path]/Telerik UI for .NET MAUI [version]/Extensions** folder - in it you'll find the **telerik.ui.for.maui.mpack** file.

* You can download the **telerik.ui.for.maui.mpack** file from your Telerik account. Go to [Download Product Files]({%slug download-product-files %}) for exact steps on how to navigate to the download page.

Then, you have to install the project wizard add-in package. Open the Visual Studio **Extension Manager** and select the *Install form file...* option:

#### Accessing Visual Studio Extensions

![Visual Studio Extensions](images/visualstudio-extensions.png)

Once you have accessed the **Extension Manager**, the following dialog will appear and you should look for the **Install from file** option.

#### Reaching the Extension Manager

![Visual Studio Extensions](images/visualstudio-extensionsmanager.png)

Navigate to the **telerik.ui.for.maui.mpack** file. 

#### The ProjectTemplate location

![Visual Studio Extensions](images/installextensionpackage.png)

If the add-in is successfully added to Visual Studio, you should see it in the **IDE** extensions section.

**Restart Visual Studio for Mac** to complete the installation.

## New Telerik .NET MAUI Blank App

Now you can create a new project using the Telerik Project Template.

#### Create New Project Dialog

![Visual Studio Create new project](images/vs-createnewproject.png)

The **telerik.ui.for.maui.mpack** template can be found in *Other > .NET* section.

#### Configure Application Dialog

![Visual Studio Configure Project](images/vs-configureproject.png)

Follow the steps to setup your app.

If you do not have the [Telerik Nuget Server]({%slug telerik-nuget-server %}) set up in Visual Studio, a message will pop up, so you can enter your Telerik credentials and the Telerik Nuget Server will be automatically configured as nuget source in Visual Studio:

![Telerik NuGet Server](images/vs_projecttemplate_nuget.png)

When you are done the project will contain all required Telerik packages, so you can start writing your app right away.

Here is the result after running the app:

![Telerik .NET MAUI Project Template](images/vs-projecttemplate-app.png)

## See Also

- [Telerik UI for .NET MAUI Toolbox]({%slug toolbox-support-mac%})
