---
title: Styling
page_title: .NET MAUI Chat Documentation - Styling
description: Learn how to style the Telerik UI for .NET MAUI Chat control.
position: 6
tags: .net maui, telerik .net maui, ui for .net maui, chat, style
slug: chat-styling
---

# .NET MAUI Chat Styling

Any change in the appearance of the `RadChat` components depends on the referenced styles. The default templates contain a `RadBorder` control (used to achieve the rounded edges), an Image control (used for the avatar of the single and first message), and a Label for the text message itself.

To customize the different parts of the control, you can use the following built-in styles:

- `MessageImageStyle`(`TargetType Image`)&mdash;Defines the style referred to the send button image.

- `OutgoingMessageImageStyle` (`TargetType Image`)&mdash;Defines the style of the outgoing message image.

- `IncomingBorderStyle` (`TargetType RadBorder`)&mdash;Defines the style of the incoming message border.

- `OutgoingBorderStyle` (`TargetType RadBorder`)&mdash;Defines the style of the outgoing message border.

- `DefaultLabelStyle` (`TargetType Label`)&mdash;Defines the default label style.

- `OutgoingLabelStyle` (`TargetType Label`)&mdash;Defines the style of the label of the outgoing message.

## Customize the Chat Entry

You can customize the `ChatEntry` with an implicit style. The example below shows how to customize the chat entry in your Chat control.

```XAML
<Style TargetType="telerik:ChatEntry">
    <Setter Property="BorderBrush" Value="{StaticResource ChatInputAreaStrokeColor}" />
    <Setter Property="FocusedBorderBrush" Value="{StaticResource ChatInputAreaStrokeColor}" />
    <Setter Property="BorderThickness" Value="1" />
    <Setter Property="CornerRadius" Value="8" />
</Style>
```

## Customize the Send Button

You can customize the send button as well. The example below shows how to customize the send button in your Chat control.

```XAML
<FontImageSource x:Key="SendIconSource"
                 FontFamily="TelerikFontExamples"
                 Glyph="&#xe82d;"
                 Color="{StaticResource ChatInputAreaStrokeColor}"
                 Size="{OnPlatform Default=24, WinUI=20}" />
```

```XAML
 <telerik:RadChat x:Name="chat"
                  BackgroundColor="{StaticResource ChatBackgroundColor}"
                  InputAreaBackgroundColor="{StaticResource ChatBackgroundColor}"
                  SendMessageButtonImage="{StaticResource SendIconSource}"/>
```
You cane see th result from the code snippets in the image below:

![.NET MAUI Chat Styling](images/chat-styling.png)








