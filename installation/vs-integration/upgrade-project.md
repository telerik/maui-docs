---
title: Upgrading Projects
meta_title: Upgrading Projects - Visual Studio Integration
description: Learn how to upgrade a Telerik UI for .NET MAUI project with the Visual Studio Upgrade Wizard.
slug: vs-integration-upgrade-project
position: 6
tag: new
---

# Upgrading Projects

This article shows how to use the [Telerik Visual Studio Extension]({%slug vs-integration-overview%}) to upgrade a project that is already configured with Telerik UI for .NET MAUI.

## Prerequisites

- Visual Studio 2022 or later with the .NET Multi-platform App UI (.NET MAUI) workload installed.
- The Telerik UI for .NET MAUI Visual Studio Extension installed and enabled.
- An open solution that contains one or more projects referencing Telerik UI for .NET MAUI.

## Upgrade a Project

The **Upgrade Project Wizard** updates the Telerik UI for .NET MAUI version used by existing applications.

1. Open the application solution in Visual Studio.

2. Open the Upgrade Wizard in one of the following ways:
   - In **Solution Explorer**, right-click the project > **Telerik UI for .NET MAUI** > **Upgrade Wizard**.
     
     ![Open the Upgrade Wizard from Solution Explorer](images/vs-upgrade-wizard-project.png)

   - From the main menu, go to **Extensions** > **Telerik** > **Telerik UI for .NET MAUI** > **Upgrade Wizard**.
     
     ![Open the Upgrade Wizard from the Extensions menu](images/vs-upgrade-wizard.png)

3. Review the introductory information, then select **Next**.

   ![Upgrade Wizard welcome screen](images/upgrade-wizard-view.png)

4. On the project selection page, select the projects to upgrade and choose the target Telerik UI for .NET MAUI version. Select **Next**.

   ![Select projects and target version](images/upgrade-wizard-versions.png)

   >tip We recommend selecting all projects that reference Telerik UI for .NET MAUI and upgrading them to the same product version.

5. (Optional) Create a backup before upgrading:
   - Enable **Create a backup before upgrade**.
   - By default, a backup is created next to the project using the project name. To change the location or name, select **Browse** and choose a destination.
   
   ![Configure backup options](images/upgrade-wizard-back-up.png)

   >tip We recommend creating a backup before you upgrade.
 
6. Select **Finish** to start the upgrade. When the process completes, review the summary page for the results and any actions taken.

   ![Upgrade summary and log](images/upgrade-wizard-log.png)

## See Also

- [Toolbox Extension for Visual Studio]({%slug toolbox-support%})
- [Scaffold Pages and Screens in Visual Studio]({%slug maui-vs-scaffoldings%})
