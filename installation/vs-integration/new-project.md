---
title: Creating New Projects
page_title: Creating New Project - Visual Studio Integration
description: Learn how to create a new Telerik UI for .NET MAUI project with the supported Visual Studio templates.
slug: vs-integration-new-project
position: 2
previous_url: /installation/windows/vs-template
---

# Creating New Projects

This article demonstrates how to use the Telerik Visual Studio extensions to create a new project that is pre-configured for the Progress&reg; Telerik&reg; UI for .NET MAUI components.

@[template](/_contentTemplates/common/extension.md#vs-extension-download)

### Extensions Menu

1. Open the **Extensions** menu in Visual Studio.
1. Select **Telerik** > **Telerik UI for .NET MAUI** > **Create New Project**.

    ![Telerik UI for .NET MAUI VS Extensions Menu](images/vsx-create-new-project-entry.png)

### Project Menu

1. Open Visual Studio and choose the **Create a new project** option.
1. Search for **telerik maui**:

    ![Create a new project dialog with maui in the search field and results](images/vsextensions_createapp.png)

1. Select one of the supported project templates:

     * **Telerik .NET MAUI App - Configurable Wizard**&mdash;Represents a configurable wizard, which contains various predefined application templates that include the Telerik .NET MAUI suite setup. 
     * **Telerik .NET MAUI Blank App**&mdash;Represents a blank project for creating a .NET MAUI application that includes the Telerik .NET MAUI suite setup.
     * **Telerik .NET MAUI Blank Shell App**&mdash;Creates a blank .NET MAUI Shell application. You can use this project as a .NET MAUI Shell example. In addition, you can use features like Shell Navigation, .NET MAUI Shell flyout, and .NET MAUI Shell tabs. For more details on .NET MAUI Shell, review the official [Microsoft documentation](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/shell/). 

## Configure the Project

1. The next step lets you configure your **Telerik UI for .NET MAUI** project by setting your project name and its location.

    ![Telerik .NET MAUI App configurable wizard initial screen within the Create your new project dialog](images/vsextensions_configureapp.png)

1. (Optional) When using the **Telerik .NET MAUI App - Configurable Wizard** project template, an additional screen for choosing the predefined application template loads:

    ![Create new project dialog in the wizard with a blank Telerik UI for .NET MAUI app](images/vsextensions_newproject-selection.png)

    * The **Telerik .NET MAUI Blank App** option creates blank application.

    * The **Telerik .NET MAUI Blank Shell App** option creates a blank .NET MAUI Shell application.

1. Choose whether to add a [theme swatch]({%slug themes-overview%}) to the project. When selecting a theme swatch, the theme configuration is automatically added to the project.

    ![Telerik .NET MAUI App configurable wizard select a theme](images/maui-select-theme.png)

1. The wizard validates your Telerik UI for .NET MAUI license and lets you download a new [license key file]({%slug set-up-your-license%}).

    ![Telerik .NET MAUI App configurable wizard license key](images/license-info-project-template.png)

Finally, Visual Studio opens the solution, which is pre-configured to use the Telerik UI for .NET MAUI controls and has the `Telerik.UI.for.Maui` NuGet package installed.

If this is the first time Visual Studio connects to the [Telerik NuGet Server]({%slug telerik-nuget-overview %}), you will see a request to enter your Telerik credentials. Then, the Telerik NuGet Server will be automatically configured as a NuGet source in Visual Studio:

![Connect to nuget.telerik.com dialog for logging your username and password](images/vsextensions_nugetpopup.png)

The following image shows the end result after running the application.

![Welcome to Telerik UI for .NET MAUI app initial screen on Windows](images/vsextensions_projecttemplate.png)

## See Also

* [Toolbox Extension for Visual Studio]({%slug toolbox-support %})
* [Scaffolding Pages and Screens in Visual Studio]({%slug maui-vs-scaffoldings%})
