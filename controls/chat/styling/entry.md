---
title: Input Area
page_title: .NET MAUI Chat Documentation - Input Area Styling
description: Learn how to style the input area of the Telerik UI for .NET MAUI Chat control.
position: 6
tags: .net maui, telerik .net maui, ui for .net maui, chat, style
slug: chat-input-area-styling
---

# .NET MAUI Chat Input Area Styling

The Telerik UI for .NET MAUI Chat control allows you to customize the appearance of its input area, by setting the `InputAreaStyle` (`Style` with target type `Telerik.Maui.Controls.Chat.ChatInputArea`) property.

The available properties for customizing the input area are:

* `BackgroundColor` (`Color`)&mdash;Defines the background color of the input area.
* `BorderColor` (`Color`)&mdash;Defines the border color of the input area.
* `BorderThickness` (`Thickness`)&mdash;Defines the border thickness of the input area.
* `CornerRadius` (`Thickness`)&mdash;Defines the corner radius of the input area.
* `ContentPadding` (`Thickness`)&mdash;Defines the padding inside the input area.
* `AttachedFilesViewStyle` (`Style` with target type `Telerik.Maui.Controls.Chat.ChatInputAreaAttachedFilesView`)&mdash;Defines the style of view of the currently attached files hat have not yet been sent.

## Style the Chat Entry

You can style the `ChatEntry` using an implicit style.

The example below shows how to customize the chat entry in your Chat control. The `Telerik.Maui.Controls.Chat.ChatEntry` represents the entry used for writing messages in the Telerik UI for .NET MAUI Chat control.

```XAML
<Style TargetType="telerik:ChatEntry">
    <Setter Property="BorderBrush" Value="{StaticResource ChatInputAreaStrokeColor}" />
    <Setter Property="FocusedBorderBrush" Value="{StaticResource ChatInputAreaStrokeColor}" />
    <Setter Property="BorderThickness" Value="1" />
    <Setter Property="CornerRadius" Value="8" />
</Style>
```

## Customize the Send Button

You can customize the icon of the send button by setting the `SendMessageButtonImage` (`ImageSource`) property.

The example below shows how to customize the Send button in your Chat control.

```XAML
<FontImageSource x:Key="SendIconSource"
                 FontFamily="Your font family name"
                 Glyph="icon code"
                 Color="Black"
                 Size="16" />
```

```XAML
 <telerik:RadChat x:Name="chat"
                  SendMessageButtonImage="{StaticResource SendIconSource}"/>
```

## See Also

- [Commands]({% slug chat-commands %})
- [Chat Items]({%slug chat-items-overview %})
- [MVVM Support]({%slug chat-mvvm-support %})