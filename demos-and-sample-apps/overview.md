---
title: Overview
page_title: .NET MAUI Examples, Demos, and Sample Apps Overview
description: "Compare Telerik .NET MAUI examples and sample apps, see what each demo covers, and learn how to switch .NET versions and run the apps locally."
slug: sampleapps-overview
tags: .net maui, ui for .net maui, .net maui controls, sample applications, demos, .net maui samples
position: 0
tag: updated
---

# .NET MAUI Examples, Demos, and Sample Apps Overview

Use this overview to choose the Telerik UI for .NET MAUI demo app that matches your goal. It explains what each sample app covers, when to use it, and how to switch .NET versions before you build the examples locally.

{% if site.has_cta_panels == true %}
{% include cta-panel-maui-overview.html %}
{% endif %}

## .NET MAUI Apps

Start with the app that matches how you want to learn: scenario-driven workflows, isolated control samples, AI integration, or a real-world dashboard. The following demo apps provide a focused path into the Telerik UI for .NET MAUI component suite:

<article-card-container>
	<article-card
		href="/demos-and-sample-apps/controls-showcase-app"
		src="images/controls-samples-android.png"
		alt="Controls Samples App preview with multiple Telerik .NET MAUI components"
		title="Controls Samples App"
		subTitle="Showcase Demo App"
		description="The Telerik UI for .NET MAUI Controls Samples app presents polished, scenario-specific use cases that highlight key features across selected components.">
	</article-card>
	<article-card
		href="/demos-and-sample-apps/crm-app"
		src="images/crm-android.png"
		alt="CRM app preview with Telerik .NET MAUI controls"
		title="CRM App"
		subTitle=".NET MAUI CRM Demo Application"
		description="The CRM app demonstrates how to build a customer relationship management application using Telerik UI for .NET MAUI controls.">
	</article-card>
	<article-card
		href="/demos-and-sample-apps/parag-demo-maui-ai"
		src="images/parag-demo-maui-ai-mobile.png"
		alt="Progress Agentic RAG Demo App preview on a mobile device"
		title="Progress Agentic RAG Demo App"
		subTitle=".NET MAUI Progress Agentic RAG Demo App"
		description="The Progress Agentic RAG Demo App shows how to integrate the Progress Agentic RAG service and AI-assisted experiences into a .NET MAUI application.">
	</article-card>
	<article-card
		href="/demos-and-sample-apps/sdkbrowser-app"
		src="images/sdk-browser-app.png"
		alt="SDKBrowser app preview with Telerik .NET MAUI control examples"
		title="SDKBrowser App"
		subTitle=".NET MAUI SDKBrowser Demo Application"
		description="The SDKBrowser app contains focused .NET MAUI samples in C# and XAML that explain how each control feature works.">
	</article-card>
	<article-card
		href="/demos-and-sample-apps/crypto-app"
		src="../images/crypto-app.png"
		alt="Crypto Tracker demo app with dashboards and market data"
		title="Crypto Tracker Demo App"
		subTitle=".NET MAUI Crypto Tracker Demo App"
		description="The Crypto Tracker demo is a real-world application that shows cryptocurrency price changes and demonstrates data-driven UI patterns built with Telerik UI for .NET MAUI.">
	</article-card>
</article-card-container>

## What Does Each .NET MAUI Demo App Help You Learn

Use this comparison table when you want to choose the most useful starting point for your current task:

| App | Best when you want to | What you will find |
|---|---|---|
| [Controls Samples App](/demos-and-sample-apps/controls-showcase-app) | Explore polished feature combinations and complete user flows | Scenario-based examples that show how multiple Telerik UI for .NET MAUI controls work together in a finished experience. |
| [CRM Demo App](/demos-and-sample-apps/crm-app) | Explore the CRM application structure and workflows | A comprehensive example that demonstrates how to build a customer relationship management application using Telerik UI for .NET MAUI controls. |
| [Progress Agentic RAG Demo App](/demos-and-sample-apps/parag-demo-maui-ai) | Learn how AI capabilities fit into a .NET MAUI application | An end-to-end example that integrates the Progress Agentic RAG service and demonstrates AI-assisted workflows. |
| [SDKBrowser App](/demos-and-sample-apps/sdkbrowser-app) | Review isolated control examples in C# and XAML | Small, focused samples that let you inspect one control feature at a time and compare implementation approaches. |
| [Crypto Tracker Demo App](/demos-and-sample-apps/crypto-app) | Study a realistic, data-driven business app | Dashboards, navigation, charts, and live-data presentation patterns built with Telerik UI for .NET MAUI controls. |

If you want fast control reference material, start with the SDKBrowser App. If you want to study app structure, polished UX flows, or production-style composition, begin with the Controls Samples App, CRM App or the Crypto Tracker Demo App.

## Download and Run the .NET MAUI Sample Apps

Open the `Examples` folder from your Telerik UI for .NET MAUI installation or downloaded `.zip` package, switch to the .NET version you want to target, and then build the app locally.

>important
> Telerik UI for .NET MAUI version `12.0.0` supports `.NET 10.0`. Before you build a sample app, switch the examples to `.NET 9.0` or `.NET 10.0` so the solution matches the SDK installed on your machine.

Use one of the following PowerShell scripts from the `Examples` folder:

```powershell
.\SwitchToNet9.ps1
.\SwitchToNet10.ps1
```

To run a sample app:

1. Open the `Examples` folder from your Telerik UI for .NET MAUI installation or downloaded `.zip` package.
2. Choose the app you want to inspect based on the scenarios in this overview.
3. Run `SwitchToNet9.ps1` or `SwitchToNet10.ps1`, depending on the SDK version you want to use.
4. Open the selected solution in Visual Studio, restore the NuGet packages, choose a device or emulator, and build the project.

## Next Steps

@[template](/_contentTemplates/common/see-also.md#see-also)