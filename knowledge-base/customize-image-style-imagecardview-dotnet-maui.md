---
title: Style the Image in the ImageCardView for .NET MAUI
description: Learn how to maintain the aspect ratio and adjust the size of images within ImageCardView in .NET MAUI applications.
type: how-to
page_title: How to Adjust Image Aspect Ratio and Size in .NET MAUI ImageCardView
slug: style-image-imagecardview-dotnet-maui
tags: chat, conversational ui, .net maui, imagecardview, aspect ratio, image size, chat image, chat
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 | Telerik UI for .NET MAUI Chat | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In .NET MAUI applications, it is often necessary to customize the appearance of images within an [`ImageCardView`]({%slug chat-imagecard%}) to fit specific design requirements. This includes maintaining the aspect ratio of displayed images and adjusting their size to fit within a particular layout without distortion. This KB article also answers the following questions:
- How to scale images without distortion in `ImageCardView`?
- How to maintain image aspect ratio in .NET MAUI applications?
- How to customize the size of images in `ImageCardView`?

## Solution

To customize the style of the image inside the `ImageCardView`, including maintaining its aspect ratio and adjusting its size you can use one of the following options:
* Apply an implicit style for the `Image` control.
* Use a `ControlTemplate`.

### Using Implicit Style

Define an implicit style targeting the `Image` type in your page resources. This style will apply to all `Image` instances within the page, allowing you to set properties like `Aspect`, `HeightRequest`, and `WidthRequest`.

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style TargetType="Image">
            <Setter Property="Aspect" Value="AspectFill"/>
            <Setter Property="HeightRequest" Value="100"/>
            <Setter Property="WidthRequest" Value="100"/>
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
```

### Using ControlTemplate

Customize the image directly within the `ControlTemplate` of the `ImageCardView`. This approach offers more flexibility for individual card customizations.

```xml
<VerticalStackLayout>
    <telerik:ImageCardView>
        <telerik:ImageCardView.ControlTemplate>
            <ControlTemplate>
                <VerticalStackLayout>
                    <Label Text="hello image one"/>
                    <Image Aspect="AspectFill"
                           HeightRequest="400"
                           WidthRequest="200" 
                           Source="dotnet_bot.png"/>
                </VerticalStackLayout>
            </ControlTemplate>
        </telerik:ImageCardView.ControlTemplate>
    </telerik:ImageCardView>
    <telerik:ImageCardView Image="emoji_wink.png"/>
    <telerik:ImageCardView Image="emoji_smile2.png"/>
</VerticalStackLayout>
```

This code snippet demonstrates how to set the aspect ratio and size for the image inside the `ImageCardView`. The `AspectFill` value ensures that the aspect ratio is maintained while the image is scaled to fill the allocated space. The `HeightRequest` and `WidthRequest` properties allow for precise control over the image dimensions.

## See Also

- [ImageCardView Overview]({%slug chat-imagecard%})
- [.NET MAUI Image Documentation](https://docs.microsoft.com/en-us/dotnet/maui/user-interface/controls/image)
