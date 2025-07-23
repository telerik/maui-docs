---
title: Using .NET CLI
page_title: Using .NET CLI
description: Learn how to use the .NET CLI to add the Telerik NuGet server as a package source in your development environment.
slug: nuget-dotnet-cli
position: 9
---

# Using .NET CLI

If you do not use a [Visual Studio's NuGet Package manager]({% slug nuget-server-vs %}) or a [custom `NuGet.Config` file]({% slug nuget-config %}), you can also add a new package source by utilizing the .NET CLI `add source` command.

Use the `add source` or `update source` command respectively to add the new source and set the credentials required for the authentication by the Telerik NuGet server.

The command below shows one way to add the Telerik NuGet source using .NET CLI. Replace the placeholders with your Telerik account username and password.

```bash
dotnet nuget add source https://nuget.telerik.com/v3/index.json --name TelerikNuGetFeed --username <TELERIK EMAIL> --password <TELERIK PASSWORD> --store-password-in-clear-text
```

>caution Storing passwords in plain text is strongly discouraged. This article uses `--store-password-in-clear-text` only for simplicity. For real-world scenarios, use secure methods, such as encrypted passwords or [API keys]({% slug nuget-config %}#generate-a-nuget-key). See <a href="https://learn.microsoft.com/en-us/nuget/consume-packages/consuming-packages-authenticated-feeds#security-best-practices-for-managing-credentials" target="_blank">Microsoft's security best practices</a> for more information on how to securely store your NuGet source credentials.

## Using an API Key

To avoid storing your Telerik account username and password in plain text on your system, use an API key instead:

1. [Generate a NuGet API Key]({% slug nuget-config %}#generate-a-nuget-key).
1. Add or update the Telerik NuGet source by using .NET CLI and the generated API key instead of a password:

    ```bash
    dotnet nuget add source https://nuget.telerik.com/v3/index.json --name TelerikNuGetFeed --username api-key --password <THE-VALUE-OF-YOUR-API-KEY> --store-password-in-clear-text
    ```

## See Also

* [Generating a NuGet API Key]({% slug nuget-config %}#generate-a-nuget-key)
* [Troubleshooting Common NuGet Setup Issues]({%slug nuget-troubleshooting%})
