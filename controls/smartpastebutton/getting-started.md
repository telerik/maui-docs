---
title: Getting Started
page_title: Getting Started with .NET MAUI SmartPasteButton
description: Get started with the Telerik UI for .NET MAUI SmartPasteButton control and add the control to your .NET MAUI project.
position: 2
slug: smartpastebutton-getting-started
---

# Getting Started with the .NET MAUI SmartPasteButton

This guide provides the information you need to start using the Telerik UI for [.NET MAUI SmartPasteButton]({%slug smartpastebutton-overview%}) by adding the control to your project.

This is the default look of the `RadSmartPasteButton` control:

![.NET MAUI SmartPasteButton Getting Started](images/smartpastebutton-default-look.gif)

## Prerequisites

Before adding the SmartPasteButton, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Configure the AI Service

@[template](/_contentTemplates/controls/ai-data-operations.md#getting-started-with-the-ai-smart-assistant)

## Process the Smart Paste Request

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

## Define the Control

**1.** When your .NET MAUI application is set up, you are ready to add a SmartPasteButton control to your page:

<snippet id='smartpastebutton-gettingstarted-xaml' />

**2.** Add the DataForm control to your page. The SmartPasteButton is designed to work in conjunction with the DataForm control, allowing you to easily populate form fields with structured data extracted from unstructured text. By integrating the SmartPasteButton with the DataForm, you can enhance the user experience and streamline data entry processes within your application.

<snippet id='smartpastebutton-gettingstarted-dataform-xaml' />

**3** For the demo, a text from the clipboard will be used for the smart paste operation.

<snippet id='smartpastebutton-gettingstarted-copy-xaml' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**5.** The copy button's `Clicked` event handler:

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
>How to do that is described in the [Configuration]({%slug smartpastebutton-configuration%}) article.

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