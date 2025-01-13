---
title: Quick Start
page_title: Telerik UI for .NET MAUI Quick Start
description: "Discover the minimum requirements for integrating Telerik UI for .NET MAUI controls into your project."
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui, macos, install, quick
slug: maui-quick-start
position: 5
---

# Quick Start with Telerik UI for .NET MAUI

This article briefly describes the basic steps for using Telerik UI for .NET MAUI in your project. If you are looking for a complete tutorial, see [First Steps with UI for .NET MAUI in Visual Studio]({%slug maui-getting-started%}) or [First Steps with UI for .NET MAUI in Visual Studio Code]({%slug maui-getting-started-vs-code%}) instead.

## Prerequisites

To create a .NET MAUI project, you need either of the following:

* <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation?view=net-maui-9.0&tabs=vswin" target="_blank">Visual Studio 2022 17.12 or later</a> with installed <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation?view=net-maui-9.0&tabs=vswin#installation-1" target="_blank">.NET MAUI workload</a>.
* <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation?view=net-maui-8.0&tabs=visual-studio-code" target="_blank">Visual Studio Code</a> with the .NET MAUI extension and the <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation?view=net-maui-8.0&tabs=visual-studio-code#install-net-and-net-maui-workloads" target="_blank">.NET and .NET MAUI workloads</a>.

## Step 1: Choose the Project Template

Depending on how you start your development with the Telerik UI for .NET MAUI controls, you may need to perform several additional steps to configure the project:

* When using the [Telerik UI for .NET MAUI project template]({%slug vs-integration-new-project%}) provided by the Telerik extensions for [Visual Studio]({%slug vs-integration-overview%}) or [Visual Studio Code]({%slug getting-started-vs-code-integration-overview%}), no additional configuration is required and you can start adding Telerik UI for .NET MAUI controls right away.
* When using the default .NET MAUI project template by Microsoft, you must also configure the Telerik namespace, register the Telerik controls, and call the `UseTelerik` extension method as described in [Configure the Project](#step-2-configure-the-project) below.

## Step 2: Configure the Project

If your .NET MAUI project uses the default project template provided by Microsoft, you must perform the steps described in this section manually.

@[template](/_contentTemplates/get-started.md#add-namespace-register-controls)

> If your project uses the `Telerik.UI.for.Maui.8.0.0` NuGet package and .NET 9, you must also install the `Microsoft.Maui.Controls.Compatibility` package. This is needed because Telerik UI for .NET MAUI version 8.0.0 depends on Microsoft's compatibility package, which is no longer included in the default **.NET MAUI App** project template. This dependency has been removed in Telerik UI for .NET MAUI version 9.0.0.

## Next Steps

* [Telerik UI for .NET MAUI Installation Approaches]({% slug installation-approaches %})
* [Restoring NuGet Packages in Your CI Workflow]({% slug nuget-keys %})

## See Also

* [First Steps with UI for .NET MAUI in Visual Studio (Tutorial)]({%slug maui-getting-started%})
* [First Steps with UI for .NET MAUI in Visual Studio Code (Tutorial)]({%slug maui-getting-started-vs-code%})
