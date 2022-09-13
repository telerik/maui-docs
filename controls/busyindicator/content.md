---
title: Custom Busy Content
page_title: .NET MAUI BusyIndicator Documentation - Custom Busy Content
description: Check our &quot;Custom Busy Content&quot; documentation article for Telerik BusyIndicator for .NET MAUI.
position: 2
previous_url: /controls/busyindicator/busyindicator-custom-busy-content
slug: busyindicator-custom-busy-content
---

# Content

This article explains the content options of the BusyIndicator when the control is and isn't busy state.

When the control is not busy you can display a content using the `Content`(View`) property.

<snippet id='busyindicator-getting-started-xaml' />

The `ContentUnderOpacity`(`double`)&mdash;Defines the opacity when the indicator is busy. the content behind the indicator is visible.

```XAML
<telerik:RadBusyIndicator x:Name="BusyIndicator" ContentUnderOpacity="0.4">
   <telerik:RadBusyIndicator.Content>
      <Label Text="This is the content of the RadBusyIndicator control displayed when the indicator is not busy." TextColor="Black" />
   </telerik:RadBusyIndicator.Content>
</telerik:RadBusyIndicator>
```

## Busy content

Setting the `BusyContent` property of BusyIndicator allows you to display any content together with the built-in animations while the control is in its Busy state. 

### Custom busy content

You can customize the `BusyContentTemplate` to arrange the custom content and the animated content per your choice.

The following example demonstrates how to customize the busy content.

Apply the `BusyContent` and `BusyContentTemplate` properties.

```XAML
<telerik:RadBusyIndicator x:Name="BusyIndicator"
						  AnimationContentHeightRequest="100"
						  AnimationContentWidthRequest="100"  
						  AnimationType="Animation6"                                            
						  IsBusy="True">           
    <telerik:RadBusyIndicator.BusyContent>
        <Label Text="Working on it, just a moment, please..." />
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
                <ContentPresenter Grid.Row="1"
                                  Content="{TemplateBinding Path=BusyContent}"
                                  HorizontalOptions="Center" />
            </Grid>
        </ControlTemplate>
    </telerik:RadBusyIndicator.BusyContentTemplate>
</telerik:RadBusyIndicator>
```

Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

The following image shows the result.

![BusyIndicator custom busy content](images/busyindicator-custombusycontent.png)

## See Also

- [BusyIndicator Animations]({% slug busyindicator-animations %})
