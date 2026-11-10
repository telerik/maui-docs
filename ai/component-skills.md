---
title: Component Skills
meta_title: Component Skills for AI Coding Assistants - Telerik UI for .NET MAUI
description: Learn how to install and use the Telerik UI for .NET MAUI Component Skills to improve AI-generated code for Telerik controls.
slug: ai-component-skills
tags: telerik,maui,dotnetmaui,ai,coding assistant,skills,component skills,agent skills
position: 2
tag: new
components: ["general"]
---

# Telerik UI for .NET MAUI Component Skills

The Telerik UI for .NET MAUI Component Skills are a set of agent skills that help AI coding assistants generate more accurate code with the [Telerik UI for .NET MAUI controls](https://www.telerik.com/maui-ui). Each agent skill contains AI-ready instructions and reference materials for a specific control or development scenario.

The public [telerik/maui-component-skills](https://github.com/telerik/maui-component-skills) GitHub repository hosts the skills.

## Why Use the Skills

AI models have general knowledge about .NET MAUI, but they may not know the latest Telerik application programming interfaces (APIs), namespaces, packages, or recommended patterns. The skills give your AI coding assistant focused Telerik context, so the assistant can:

* Generate code with the correct Telerik APIs, namespaces, and NuGet packages.
* Follow recommended Telerik UI for .NET MAUI implementation patterns.
* Configure advanced control features and common development scenarios.
* Provide Telerik-specific setup, licensing, theming, migration, and troubleshooting guidance.
* Reduce incorrect or outdated API suggestions.

## Compare the Skills and the MCP Server

The Component Skills and the [Telerik MAUI Model Context Protocol (MCP) Server]({%slug ai-mcp-server%}) are complementary. The following table compares the two tools:

| Aspect | Component Skills | MCP Server |
|---|---|---|
| Delivery | Markdown files added to your project or AI assistant | Server process that your MCP client runs |
| How the assistant uses them | The assistant loads the relevant skill based on your prompt | The assistant calls the server tool during a chat or agent session |
| Setup | Install once with `npx` or copy the files | Install the NuGet tool and configure `mcp.json` |

You can use the skills on their own or together with the MCP Server.

## Prerequisites

To use the Telerik UI for .NET MAUI Component Skills, you need:

* An AI coding assistant that supports agent skills or compatible context mechanisms, for example, GitHub Copilot, Cursor, or Claude Code.
* [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0) or [.NET 11 SDK](https://dotnet.microsoft.com/download/dotnet/11.0).
* A Telerik UI for .NET MAUI license. You can start a [free trial](https://www.telerik.com/try/ui-for-maui). For more details, see [Set Up Your Telerik License]({%slug set-up-your-license%}).
* [Node.js](https://nodejs.org/en) if you install the skills with `npx`.

## Install the Skills

You can install the skills with `npx` or copy them manually from the GitHub repository.

### Install with npx

Run the following command in your project folder:

```bash
npx skills add https://github.com/telerik/maui-component-skills
```

The command adds the skills to your project so that your AI coding assistant can discover them.

### Install Manually

As an alternative, clone the repository:

```bash
git clone https://github.com/telerik/maui-component-skills.git
```

Then make the content of the `skills` folder available to your project according to the requirements of your AI coding assistant.

>note Installation and skill discovery differ between AI coding assistants. Check the documentation of your assistant for the folder where it expects skills.

## How the Skills Work

Each skill provides focused knowledge about a single Telerik control or development scenario:

```text
skills/
└── telerik-maui-<control>/
    ├── SKILL.md
    └── references/
        ├── getting-started.md
        ├── overview.md
        └── ...
```

* `SKILL.md`&mdash;Describes when the assistant must use the skill, the relevant control, packages, namespaces, and APIs, the recommended implementation workflows, and links to deeper reference material.
* `references/`&mdash;Contains detailed guidance for specific scenarios, such as setup, data binding, styling, advanced features, and troubleshooting.

When you describe a task, the AI coding assistant identifies the matching skill and loads only the reference material that it needs for the task.

## Use the Skills

In most cases, you do not need to specify which skill to use. Describe the Telerik control and what you want to accomplish:

```text
Create a Telerik MAUI DataGrid that displays a list of orders.
Add sorting and filtering.
Allow users to edit the Quantity column.
Export the data to Excel.
```

For more precise results, add relevant application context, such as your .NET version, architecture, data source, and desired behavior:

```text
I'm building a .NET MAUI application using MVVM.
Create a Telerik Scheduler with appointments coming from an ObservableCollection.
Add week and month views and support recurring appointments.
```

To make your intent clearer, you can also mention the skill explicitly:

```text
Use the Telerik MAUI DataGrid skill to add filtering to this DataGrid.
```

### Sample Prompts

The following prompts demonstrate common scenarios that the skills support:

* Getting started&mdash;"`Set up Telerik UI for .NET MAUI in my application.`"
* Building UI&mdash;"`Create a Telerik CollectionView with grouping and sticky headers.`"
* Advanced features&mdash;"`Add filtering, grouping, and Excel export to my Telerik DataGrid.`"
* Styling and theming&mdash;"`Create a custom Telerik theme and allow users to switch themes at runtime.`"
* Migration&mdash;"`Migrate my Telerik Xamarin.Forms DataGrid to .NET MAUI.`"
* Troubleshooting&mdash;"`My Telerik Scheduler appointments are not appearing. Help me troubleshoot the setup.`"

>warning Always double-check the suggested code and solutions of any AI-powered tool before applying them to your app.

## Available Skills

The Component Skills cover the Telerik UI for .NET MAUI controls and the common development scenarios, such as getting started, theming, localization, font icons, and migration from Xamarin.Forms.

For the current list of skills with links to each skill, see the [Skill Index](https://github.com/telerik/maui-component-skills#skill-index) in the repository.

>tip If you are setting up a new project, start with the Getting Started skill.

## Keep the Skills Up to Date

The Telerik UI for .NET MAUI team maintains the skills and updates them as the product evolves. To get the latest guidance, run the `npx skills add` command again or pull the latest changes from the repository.

## Report Issues with the Skills

If a skill produces outdated, incomplete, or incorrect guidance, [open an issue](https://github.com/telerik/maui-component-skills/issues) in the repository and include:

* The prompt you used.
* The generated result or relevant code.
* The expected result.
* Your Telerik UI for .NET MAUI version.
* The AI coding assistant you used.

## See Also

* [Agentic UI Generator Overview]({%slug ai-overview%})
* [Getting Started with the Telerik MAUI MCP Server]({%slug ai-mcp-server%})
* [Prompt Library]({%slug ai-prompt-library%})
* [Telerik UI for .NET MAUI Component Skills on GitHub](https://github.com/telerik/maui-component-skills)
