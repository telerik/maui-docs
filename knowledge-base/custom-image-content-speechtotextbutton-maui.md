---
title: Adding Custom Image as Content to SpeechToTextButton in UI for .NET MAUI
description: Learn how to add a custom image as content to the SpeechToTextButton in UI for .NET MAUI.
type: how-to
page_title: Using Custom Image Content for SpeechToTextButton in .NET MAUI
meta_title: Using Custom Image Content for SpeechToTextButton in .NET MAUI
slug: custom-image-content-speechtotextbutton-maui
tags: speechtotextbutton, ui-for-net-maui, content, image, button
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 12.0.0 | Telerik UI for .NET MAUI SpeechToTextButton | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to add a custom SVG image, such as a pause icon, as content to the [SpeechToTextButton](https://www.telerik.com/maui-ui/documentation/controls/speechtotextbutton/overview) in UI for .NET MAUI. Adding the image directly to the `Content` property doesn't work, as the property converts strings to labels instead of images. How can I achieve this?

This knowledge base article also answers the following questions:
- How to set an SVG image as the content of SpeechToTextButton?
- How to customize the content of SpeechToTextButton using an image?
- How to use a visual state to display an image in SpeechToTextButton?

## Solution

To set a custom image as the content of the SpeechToTextButton, define an `Image` resource and use it in a style for the button. Follow these steps:

1. Define the image resource in your XAML code.

   ```xml
   <Image x:Key="MyContent" Source="pause_icon.svg" />
   ```

2. Create a style for the SpeechToTextButton, specifying the `Content` property in the `VisualState.Setters`.

   ```xml
   <Style x:Key="SpeechToTextButtonStyle" TargetType="telerik:RadSpeechToTextButton">
       <Setter Property="Padding" Value="12, 8" />
       <Setter Property="CornerRadius" Value="12" />
       <Setter Property="VerticalTextAlignment" Value="Center" />
       <Setter Property="HorizontalTextAlignment" Value="Center" />
       <Setter Property="TextColor" Value="#00897B" />
       <Setter Property="BackgroundColor" Value="Transparent" />
       <Setter Property="BorderBrush" Value="LightGray" />
       <Setter Property="BorderThickness" Value="2" />
       <Setter Property="VisualStateManager.VisualStateGroups">
           <VisualStateGroupList>
               <VisualStateGroup Name="CommonStates">
                   <VisualState Name="Normal">
                       <VisualState.Setters>
                           <Setter Property="telerik:RadSpeechToTextButton.Content" Value="{StaticResource MyContent}" />
                       </VisualState.Setters>
                   </VisualState>
                   <VisualState Name="Pressed">
                       <VisualState.Setters>
                           <Setter Property="telerik:RadSpeechToTextButton.Content" Value="{StaticResource MyContent}" />
                           <Setter Property="telerik:RadSpeechToTextButton.TextColor" Value="#9900897B" />
                           <Setter Property="telerik:RadSpeechToTextButton.BackgroundColor" Value="#E8F5F4" />
                       </VisualState.Setters>
                   </VisualState>
                   <VisualState Name="Listening">
                       <VisualState.Setters>
                           <Setter Property="telerik:RadSpeechToTextButton.Content" Value="{StaticResource MyContent}" />
                           <Setter Property="telerik:RadSpeechToTextButton.TextColor" Value="#000000" />
                           <Setter Property="telerik:RadSpeechToTextButton.BackgroundColor" Value="#00897B" />
                       </VisualState.Setters>
                   </VisualState>
               </VisualStateGroup>
           </VisualStateManager.VisualStateGroups>
       </Setter>
   </Style>
   ```

## See Also

- [SpeechToTextButton Documentation](https://www.telerik.com/maui-ui/documentation/controls/speechtotextbutton/overview)
- [SpeechToTextButton Styling in .NET MAUI](https://www.telerik.com/maui-ui/documentation/controls/speechtotextbutton/styling)
