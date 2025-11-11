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

To customize the icon of the send button, use the `SendMessageButtonImage` (`ImageSource`) property.

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

The More button provides additional options for the user, such as attaching files or accessing other functionalities.

You can configure and style the More button using the following properties:

* `IsMoreButtonVisible` (`bool`) property controls the visibility of the more button. The default value is `false`.

* `AutoGenerateMoreButtonActions `(`bool`)&mdash;Defines whether to automatically generate default actions for the 'More' button. The default value is `true`.

* Define the actions that will appear when the More button is tapped by adding instances of `ChatMoreButtonAction` to the `MoreButtonActions` (`IList<ChatMoreButtonAction>`) collection.

* Style the More button using the `MoreButtonStyle` (`Style` with target type `Telerik.Maui.Controls.Chat.ChatMoreButtonToolbarItemView`) property.

## Style the SpeechToTextButton

To configure the SpeechToTextButton, use the following properties:

* `IsSpeechToTextButtonVisible` (`bool`) property controls the visibility of the SpeechToTextButton. By default, the button is visible on Android, iOS and MacCatalyst and not visible on Windows.

* `SpeechToTextButtonStyle` (`Style` with target type `Telerik.Maui.Controls.RadSpeechToTextButton`) property is used to style the SpeechToTextButton.

## See Also

- [Commands]({%slug chat-commands%})
- [Chat Items]({%slug chat-items-overview%})
- [MVVM Support]({%slug chat-mvvm-support%})