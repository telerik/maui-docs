---
title: Create New Project
page_title: Create New Project - Visual Studio Code Integration
description: Learn how to create a new Telerik UI for .NET MAUI project with our Visual Studio Code Templates.
slug: getting-started-vs-code-integration-new-project
position: 1
---

# Create New Projects

This article demonstrates how to use the Telerik Extension for Visual Studio Code to create a new project that is pre-configured for the Progress&reg; Telerik&reg; UI for .NET MAUI components.

## Get the Extension

To use the **Telerik UI for .NET MAUI Template Wizard**, install the `Telerik UI for .NET MAUI Productivity Tools` extension. You can get the extension from:

* <a href="https://marketplace.visualstudio.com/items?itemName=TelerikInc.telerik-maui-productivity-tools" target="_blank">The Visual Studio Code Marketplace.</a>

* The **Extensions** tab in Visual Studio Code&mdash;search for `Telerik UI for .NET MAUI Productivity Tools`, select the extension, and then click **Install**.

## Start the Wizard

You can create a Telerik .NET MAUI project by accessing the project template feature from the Visual Studio Code Extensions menu. To open the menu, use:

 - `Ctrl+Shift+P` on Windows/Linux 
 - `Cmd+Shift+P` on Mac. 

Next, select **Telerik UI for .NET MAUI Template Wizard: Launch** from the menu and press **Enter**. 

![Telerik UI for .NET MAUI VS Code snippets](images/MauiTemplateWizard.gif)

## Set Up the Telerik NuGet Server

By using the Telerik NuGet server, you can install the packages with the Telerik UI for .NET MAUI controls. As the server requires authentication, you can use one of the following options to configure the required credentials for your Telerik license (trial or commercial):

* [Using the .NET CI]({%slug nuget-keys%})
* [Editing the `NuGet.Config` File]({%slug nuget-config%})

## Select a Project

The Create New Project wizard provides two options to start you project:

 -  Blank App&mdash;Allows you to create a blank project that is pre-configured for the Progress® Telerik® UI for .NET MAUI components.
 -  Blank Shell App&mdash;Allows you to create a blank shell project that is pre-configured for the Progress® Telerik® UI for .NET MAUI components.

## Configure the Project

The wizard allows you to configure the following options:

  - Project name
  - Location of the created project (Output Path)
  - Your Telerik license (trial or commercial)
  - The .NET version you want to use