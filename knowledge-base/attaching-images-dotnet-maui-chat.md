---
title: Attaching and Displaying Images in .NET MAUI Chat
description: Learn how to attach and display images in the .NET MAUI Chat (Conversational UI) component using custom templates and logic.
type: how-to
page_title: How to Attach Images in .NET MAUI Chat Control
slug: attaching-images-dotnet-maui-chat
tags: chat, conversational-ui, .net-maui, image-upload, item-template-selector
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI Chat | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to know how to attach an image in the .NET MAUI Chat and display the image in the conversation. This requires implementing custom logic for uploading images and creating a custom `ItemTemplate` for rendering messages with images. 

This knowledge base article also answers the following questions:
- How to upload an image in .NET MAUI Chat?
- How to create a custom template for images in .NET MAUI Chat?
- How to use `ItemTemplateSelector` to manage media content in .NET MAUI Chat?

## Solution

The steps below describe two states for using images in the Chat control:
1. Add additional UI element for uploading images in the conversation.
2. Display the uploaded images in the conversation. 

### Add Image or Camera Button 

To add additional UI element to the Chat entry area, you need to define a custom control template and include an image button.

Here is an example of the control template with image button.

**1.** Define the `ControlTemplate` to the page's resources:

```xml
 <ControlTemplate x:Key="RadChatControlTemplate">
        <Grid IsClippedToBounds="True">
            <Grid telerikMauiControls:KeyboardHelper.IsTranslationTarget="True"
                  IsClippedToBounds="True"
                  RowSpacing="2"
                  RowDefinitions="*, Auto">
                <Grid Margin="{OnPlatform Default='10, 10, 10, 0', WinUI='0, 10, 0, 0', MacCatalyst='0, 10, 0, 0'}">
                    <telerikChat:RadChatListView x:Name="PART_ChatListView"
                                                 telerikMauiControls:StyleHelper.InheritedStyleClass="{TemplateBinding ActualStyleClass}"
                                                 AutoScrollMode="{TemplateBinding AutoScrollMode}"
                                                 ScrollMediator="{TemplateBinding ActualScrollMediator}"
                                                 ItemTemplate="{TemplateBinding ItemTemplateSelector}"
                                                 ItemsSource="{TemplateBinding Items}"
                                                 AutomationId="RadChatListView" />
                    <telerikMauiControls:RadContentView telerikMauiControls:StyleHelper.InheritedStyleClass="{TemplateBinding ActualStyleClass}"
                                                        VerticalOptions="End"
                                                        Content="{TemplateBinding TypingIndicator}"
                                                        HeightRequest="{TemplateBinding TypingIndicator.IsVisible, Converter={StaticResource ChatBoolToValueConverter}}"
                                                        Padding="{OnPlatform Default=0, WinUI='10, 0', MacCatalyst='12, 0'}" />
                    <telerikMauiControls:RadContentView telerikMauiControls:StyleHelper.InheritedStyleClass="{TemplateBinding ActualStyleClass}"
                                                        VerticalOptions="End"
                                                        Content="{TemplateBinding Picker}"
                                                        HeightRequest="{TemplateBinding Picker.IsVisible, Converter={StaticResource ChatBoolToValueConverter}}"
                                                        MaximumHeightRequest="{Binding Height, Source={x:Reference PART_ChatListView}}"
                                                        Padding="{OnPlatform Default=0, WinUI='10, 0', MacCatalyst='12, 0'}" />
                </Grid>
                <Grid x:Name="PART_InputAreaGrid"
                      Grid.Row="1"
                      ColumnDefinitions="*, Auto"
                      Padding="10"
                      telerikMauiControls:KeyboardHelper.IsTranslationPivot="True">
                    <telerikChat:ChatEntry x:Name="PART_ChatEntry"
                                           telerikMauiControls:StyleHelper.InheritedStyleClass="{TemplateBinding ActualStyleClass}"
                                           ReserveSpaceForErrorView="False"
                                           Keyboard="Chat"
                                           Text="{TemplateBinding Message, Mode=TwoWay}"
                                           HeightRequest="{OnPlatform Default=36, WinUI=32, MacCatalyst=28, Android=44}"
                                           ReturnCommand="{TemplateBinding ActualSendMessageCommand}"
                                           BackgroundColor="Transparent"
                                           VerticalOptions="Center"
                                           telerikMauiControls:KeyboardHelper.IsTranslationSource="True" 
                                           AutomationId="RadChatEntry" />
                    <ImageButton x:Name="PART_SendMessageButton"
                                 Grid.Column="1"
                                 telerikMauiControls:StyleHelper.InheritedStyleClass="{TemplateBinding ActualStyleClass}"
                                 Opacity="0.6"
                                 Padding="0"
                                 Margin="10, 0, 0, 0"
                                 Command="{TemplateBinding ActualSendMessageCommand}"
                                 Source="{Binding SendMessageButtonImage, Source={RelativeSource Mode=TemplatedParent}}"
                                 BackgroundColor="Transparent"
                                 BorderColor="Transparent"
                                 WidthRequest="{OnPlatform Default=24, WinUI=22}"
                                 Aspect="AspectFit"
                                 VerticalOptions="Center" 
                                 AutomationId="RadChatSendMessageButton" />

<!--
add additional elements here <ImageButton /> or <telerik:RadTemplatedButton />
 --> 
<ImageButton />
                </Grid>
            </Grid>
        </Grid>
    </ControlTemplate>
```

**2.** Set this template to the `RadChat` control using the following syntax:

```xml
<telerik:RadChat ControlTemplate="{StaticResource RadChatControlTemplate}" />
```

### Display Image in Conversation

Use the following steps to display images in the chat:

**1.** Implement the logic for uploading images in the button's command.
>note To handle image uploads in .NET MAUI, you need to ensure your application has the necessary permissions to access the device's storage and camera.

**2.** Create a custom `ItemTemplate` to display image messages.
**3.** Use the `ItemTemplateSelector` to dynamically choose templates based on message content.

Follow the steps outlined in the [`ItemTemplateSelector` documentation](https://docs.telerik.com/devtools/maui/controls/chat/item-template-selector) to configure this functionality.

Example of an `ItemTemplate` for rendering messages with images:

```xml
<DataTemplate x:Key="ImageMessageTemplate">
    <Image Source="{Binding ImageSource}" Aspect="AspectFit" WidthRequest="100" HeightRequest="100" />
</DataTemplate>
```

Use the `ItemTemplateSelector` to assign this template conditionally based on the message type.

## See Also

- [Chat Control Documentation](https://docs.telerik.com/devtools/maui/controls/chat/overview)
- [Chat ItemTemplateSelector Documentation](https://docs.telerik.com/devtools/maui/controls/chat/item-template-selector)
