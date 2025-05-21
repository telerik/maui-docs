---
title: Adding an Image Inside the BusyIndicator for .NET MAUI
description: Learn how to add an image inside the BusyIndicator for .NET MAUI when the IsBusy property is set to true.
type: how-to
page_title: How to Add Image Inside BusyIndicator in .NET MAUI
slug: add-image-inside-busyindicator-dotnet-maui
tags: busyindicator,.net maui,isbusy,busycontent,busycontenttemplate,image
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI BusyIndicator | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to display an image inside the BusyIndicator while the busy animation appears when the `IsBusy` property is set to `true`. 

This knowledge base article also answers the following questions:
- How to customize the BusyIndicator's content in .NET MAUI?
- How to display an image and text inside BusyIndicator for .NET MAUI?
- How to use the BusyContentTemplate of BusyIndicator for .NET MAUI?

## Solution

To add an image inside the BusyIndicator for .NET MAUI, define a custom busy content using the `BusyContent` and `BusyContentTemplate` properties. This allows you to display an image along with other custom elements while the busy animation appears.

### Steps

1. Use the `RadBusyIndicator.BusyContent` property to define the image and any additional elements you want to display.
2. Use the `RadBusyIndicator.BusyContentTemplate` property to create a custom layout for the busy content.

Here is the BusyIndicator definition in XAML:

```xml
<telerik:RadBusyIndicator x:Name="busyIndicator" 
                          IsVisible="{Binding IsBusyBusyIndicator}"
                          AnimationContentHeightRequest="100"
                          AnimationContentWidthRequest="100"
                          AnimationContentColor="{DynamicResource PrimaryColor}"
                          IsBusy="{Binding IsBusyBusyIndicator}"
                          BackgroundColor="#CCDCDCDC">
  <telerik:RadBusyIndicator.BusyContent>
    <VerticalStackLayout>
      <Image Source="yourimage.png" HeightRequest="30" WidthRequest="30" BackgroundColor="{DynamicResource PrimaryColor}" />
      <Label Text="Loading..." HorizontalOptions="Center" VerticalOptions="Center"/>
    </VerticalStackLayout>
  </telerik:RadBusyIndicator.BusyContent>
  <telerik:RadBusyIndicator.BusyContentTemplate>
    <ControlTemplate>
      <Grid>
        <Grid.RowDefinitions>
          <RowDefinition Height="Auto" />
          <RowDefinition Height="Auto" />
          <RowDefinition Height="*" />
        </Grid.RowDefinitions>
        <ContentPresenter Content="{TemplateBinding Path=AnimationContent}" />
        <ContentPresenter Content="{TemplateBinding Path=BusyContent}" Margin="30"
                          Grid.Row="0" Grid.RowSpan="2"
                          HorizontalOptions="Center" VerticalOptions="Center"/>
      </Grid>
    </ControlTemplate>
  </telerik:RadBusyIndicator.BusyContentTemplate>
</telerik:RadBusyIndicator>
```

### Explanation

- `BusyContent`&mdash;Defines the content displayed during the busy state, such as an image and text.
- `BusyContentTemplate`&mdash;Creates a custom layout that combines the busy animation and the busy content.

Adjust the properties such as `Source`, `HeightRequest`, and `WidthRequest` for the image to suit your requirements.

## See Also

- [BusyIndicator Documentation](https://docs.telerik.com/devtools/maui/controls/busyindicator/overview)
- [Custom Busy Content Documentation](https://docs.telerik.com/devtools/maui/controls/busyindicator/content#custom-busy-content) 
- [BusyIndicator API Reference](https://docs.telerik.com/devtools/maui/api/Telerik.Maui.Controls.RadBusyIndicator) 
