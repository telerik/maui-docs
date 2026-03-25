---
title: Using Focus and Unfocus Events in Telerik UI for .NET MAUI Chat
description: Learn how to handle focus and unfocus events in Telerik UI for .NET MAUI Chat by accessing the RadMultilineTextInput control within the chat template.
type: how-to
page_title: Handle Focus and Unfocus Events in Telerik UI for .NET MAUI Chat
meta_title: Handle Focus and Unfocus Events in Telerik UI for .NET MAUI Chat
slug: handle-focus-unfocus-events-maui-chat
tags: telerik, ui for .net maui, chat, radmultilinetextinput, focus, unfocus
res_type: kb
ticketid: 1711957
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 13.0.0 | Telerik UI for .NET MAUI Chat | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to handle the focus and unfocus events in the [Telerik UI for .NET MAUI Chat](https://www.telerik.com/maui-ui/documentation/controls/chart/overview) control. The `RadMultilineTextInput` is used as the input element within the Chat's `PromptInput`. How can I access the required events?

This knowledge base article also answers the following questions:

- How to attach focus and unfocus events to the Chat input field in Telerik UI for .NET MAUI?
- How to handle focus events in Chat for .NET MAUI?
- How to subscribe to `RadMultilineTextInput` events in Telerik UI for .NET MAUI?

## Solution

To handle the focus or unfocus event in Telerik UI for .NET MAUI Chat, access the `RadMultilineTextInput` inside the Chat's `PromptInput` on the `Loaded` event of the Chat control. Follow these steps:

1. Subscribe to the `Loaded` event of the Chat control.
2. Access the visual tree descendants of the Chat to locate the `RadMultilineTextInput`.
3. Attach the `Focused` or `Unfocused` event to the `RadMultilineTextInput`.

Here is an example implementation:

```csharp
private void Chat_Loaded(object sender, EventArgs e)
{
    // Get all visual tree descendants of the chat control
    List<IVisualTreeElement> items = (List<IVisualTreeElement>)this.chat.GetVisualTreeDescendants();
    
    foreach (IVisualTreeElement myControl in items)
    {
        // Check if the control is RadMultilineTextInput
        if (myControl is RadMultilineTextInput)
        {
            RadMultilineTextInput control = (RadMultilineTextInput)myControl;
            
            // Attach the Focused event
            control.Focused += Control_Focused;
            return;
        }
    }
}

// Handle the Focused event
private void Control_Focused(object? sender, FocusEventArgs e)
{
    // Add your logic for handling focus here
}
```

Below is the XAML definition of the Chat control with the `Loaded` event attached:

```xml
<telerik:RadChat x:Name="chat" Grid.Row="1"
                  Author="{Binding Me}"
                  Loaded="Chat_Loaded"
                  ItemsSource="{Binding Items}" 
                  ItemConverter="{StaticResource SimpleChatItemConverter}">
    <telerik:RadChat.BindingContext>
        <local:ViewModel />
    </telerik:RadChat.BindingContext>
</telerik:RadChat>
```

This method enables handling the focus and unfocus events for the input field in the Telerik UI for .NET MAUI Chat control.

## See Also

- [Telerik UI for .NET MAUI Chat Documentation](https://www.telerik.com/maui-ui/documentation/controls/chart/overview)
- [MultilineTextInput Documentation](https://www.telerik.com/maui-ui/documentation/controls/editor/multiline-text-input)
