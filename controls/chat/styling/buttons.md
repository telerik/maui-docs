---
title: Buttons
page_title: .NET MAUI Chat Documentation - Buttons Styling
description: Learn how to style the buttons inside the Telerik UI for .NET MAUI Chat control.
position: 6
tags: .net maui, telerik .net maui, ui for .net maui, chat, style
slug: chat-buttons-styling
---

# .NET MAUI Chat Buttons Styling

This section describes how to style the send, more and speech to text buttons inside the `RadChat` control.

## Style the Send Button

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

## Style the More Button

Control the visibility of the more button by setting the `IsMoreButtonVisible` (`bool`) property to `true`. The default value is `false`.

* `AutoGenerateMoreButtonActions `(`bool`)&mdash;Defines whether to automatically generate default actions for the 'More' button. The default value is `true`.

Style the MoreButton using the `MoreButtonStyle` (`Style` with target type `Telerik.Maui.Controls.Chat.ChatMoreButtonToolbarItemView`) property.

## Style the SpeechToTextButton

You can control the SpeechToTextButton visibility by setting the `IsSpeechToTextButtonVisible` (`bool`) property. By default, the button is visible on Android, iOS and MacCatalyst and not visible on Windows. 

To style the SpeechToTextButton, use the `SpeechToTextButtonStyle` (`Style` with target type `Telerik.Maui.Controls.RadSpeechToTextButton`) property.

## See Also

- [Commands]({%slug chat-commands%})
- [Chat Items]({%slug chat-items-overview%})
- [MVVM Support]({%slug chat-mvvm-support%})