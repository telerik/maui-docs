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

- `MessageImageStyle`(target type `Image`)&mdash;Defines the style referred to the send button image.

- `OutgoingMessageImageStyle` (target type `Image`)&mdash;Defines the style of the outgoing message image.

- `IncomingBorderStyle` (target type `RadBorder`)&mdash;Defines the style of the incoming message border.

- `OutgoingBorderStyle` (target type `RadBorder`)&mdash;Defines the style of the outgoing message border.

- `DefaultLabelStyle` (target type `Label`)&mdash;Defines the default label style.

- `OutgoingLabelStyle` (target type `Label`)&mdash;Defines the style of the label of the outgoing message.

In addition, the following properties set the background of the Chat:

* `BackgroundColor`(`Color`)&mdash;Defines the background color of the Chat control.
* `InputAreaBackgroundColor`(`Color`)&mdash;Defines the bacgkround color of the area that the input elements (entry and button) reside.

## Customize the Chat Entry

You can customize the `ChatEntry` with an implicit style. The example below shows how to customize the chat entry in your Chat control. The `ChatEntry` represents the entry used for writing messages in the Telerik UI for .NET MAUI Chat control.

```XAML
<Style TargetType="telerik:ChatEntry">
    <Setter Property="BorderBrush" Value="{StaticResource ChatInputAreaStrokeColor}" />
    <Setter Property="FocusedBorderBrush" Value="{StaticResource ChatInputAreaStrokeColor}" />
    <Setter Property="BorderThickness" Value="1" />
    <Setter Property="CornerRadius" Value="8" />
</Style>
```

## Customize the Send Button

The example below shows how to customize the Send button in your Chat control.

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
You cane see the result from the code snippets in the image below:

![.NET MAUI Chat Styling](images/chat-styling.png)

## See Also

- [Commands]({% slug chat-commands %})
- [Chat Items]({%slug chat-items-overview %})
- [MVVM Support]({%slug chat-mvvm-support %})