---
title: Getting Started
page_title: Getting Started with .NET MAUI SmartPasteButton
description: Get started with the Telerik UI for .NET MAUI SmartPasteButton control and add the control to your .NET MAUI project.
position: 2
slug: smartpastebutton-getting-started
---

# Getting Started with the .NET MAUI SmartPasteButton

This guide provides the information you need to start using the Telerik UI for [.NET MAUI SmartPasteButton]({%slug smartpastebutton-overview%}) by adding the control to your project.

The following image shows the default look of the `RadSmartPasteButton` control:

![.NET MAUI SmartPasteButton Getting Started](images/smartpastebutton-default-look.gif)

## Prerequisites

Before adding the SmartPasteButton, you need to:

1. Install`.NET9` or later.

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

1. Install an AI provider. For example **Azure OpenAI** or **OpenAI**, etc.

## Step 1: Configure the AI Service

1. Install the [`Telerik.AI.SmartComponents.Extensions`](https://www.nuget.org/packages/Telerik.AI.SmartComponents.Extensions) package in your .NET MAUI project.

```script
dotnet add package Telerik.AI.SmartComponents.Extensions
```
```xml
<PackageReference Include="Telerik.AI.SmartComponents.Extensions" Version="Select Latest" />
```

>tip The `Telerik.AI.SmartComponents.Extensions` package has a dependency on the `Microsoft.Extensions.AI` package.

2. Configure the AI services in your application. This typically involves setting up an AI provider (such as **Azure OpenAI**, **OpenAI**, etc.) and providing the necessary API keys or credentials.

3. Register the AI service and AI chat client in your application.

    For the example, we will use the `Azure.AI.OpenAI` and `Microsoft.Extensions.AI.OpenAI` packages. Add the packages to your project. To register the AI service and chat client, the following code is needed in `MauiProgram.cs`:

    ```C#
    builder.Services.AddSingleton(sp =>
    {
        return new AzureOpenAIClient(new Uri("AZURE_OPENAI_ENDPOINT"), new AzureKeyCredential("AZURE_OPENAI_API_KEY"));
    });

    builder.Services.AddChatClient(services =>
        services.GetRequiredService<AzureOpenAIClient>().GetChatClient("gpt-4.1").AsIChatClient()
    );
    ```

## Step 2: Process the Smart Paste Request

Inside the `SmartPasteRequest` event handler or in the command that processes the smart paste request, you need to create a `SmartPasteRequest` object with the content and form fields from the event arguments, send it to your AI service, and set the response back to the event arguments.

Here is an example of how to do this:

```C#
private async void OnSmartPasteRequest(object sender, SmartPasteButtonRequestContext e)
{
    try
    {
        var chatClient = Application.Current.Handler.MauiContext.Services.GetRequiredService<IChatClient>();

        var request = new SmartPasteRequest
        {
            Content = e.Content,
            FormFields = e.Fields.Select(f => new SmartPasteFormField
            {
                Field = f.Field,
                Description = f.Description,
                AllowedValues = f.AllowedValues,
                Type = f.Type
            }).ToArray()
        };

        List<ChatMessage> conversationMessages = request.GetChatMessages();
        ChatResponse completion = await chatClient.GetResponseAsync(conversationMessages, new ChatOptions(), e.CancellationToken);
        e.SetResponse(completion.ExtractSmartPasteResponse().FieldValues);
    }
    catch (OperationCanceledException)
    {
        e.Cancel();
    }
    catch (Exception ex)
    {
        await ShowErrorAsync($"Smart paste failed: {ex.Message}");
        e.SetError(ex);
    }
}
```

>tip Review the [Integration with External UI]({%slug smartpastebutton-external-ui-integration%}) article for more details how to integrate the Telerik SmartPasteButton for .NET MAUI with external UI components to enhance user experience.

## Example with SmartPasteButton and DataForm

**1.** Define the SmartPasteButton control to your page:

<snippet id='smartpastebutton-gettingstarted-xaml' />

**2.** Add the DataForm control to your page. The SmartPasteButton is designed to work with the DataForm control, allowing you to populate form fields with structured data extracted from unstructured text. By integrating the SmartPasteButton with the DataForm, you can enhance the user experience and streamline data entry processes within your application.

<snippet id='smartpastebutton-gettingstarted-dataform-xaml' />

**3.** Text from the clipboard is used for the smart paste operation.

<snippet id='smartpastebutton-gettingstarted-copy-xaml' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**5.** Define the copy button's `Clicked` event handler:

<snippet id='smartpaste-gettingstarted-copy' />

**6.** The `SmartPasteRequest` event handler:

<snippet id='smartpaste-gettingstarted-paste-request' />

**7.** Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

```C#
using Telerik.Maui.Controls.Compatibility;
public static class MauiProgram
{
	public static MauiApp CreateMauiApp()
	{
		var builder = MauiApp.CreateBuilder();
		builder
			.UseTelerik()
			.UseMauiApp<App>()
			.ConfigureFonts(fonts =>
			{
				fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
			});
		return builder.Build();
	}
}
```

>important The SmartPasteButton examples in the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) use a Telerik-hosted AI service for demonstration purposes only. 
>
>To use the smart paste functionality in your application, you must configure your own AI service.
>
>How to do that is described in the [Configuration]({%slug smartpastebutton-getting-started%}#step-1-configure-the-ai-service) article.

> For a runnable example with the SmartPasteButton Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **SmartPasteButton > Getting Started**.

## Additional Resources

- [.NET MAUI SmartPasteButton Product Page](https://www.telerik.com/maui-ui/smartpastebutton)
- [.NET MAUI SmartPasteButton Forum Page](https://www.telerik.com/forums/maui?tagId=smartpastebutton)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Styling the SmartPasteButton]({%slug smartpastebutton-styling%})
- [Visual States of the SmartPasteButton]({%slug smartpastebutton-visual-states%})
- [Events of the SmartPasteButton]({%slug smartpastebutton-events%})
- [Commanding with the SmartPasteButton]({%slug smartpastebutton-command%})