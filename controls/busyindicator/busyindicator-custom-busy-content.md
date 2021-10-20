---
title: Custom Busy Content
page_title: .NET MAUI BusyIndicator Documentation | Custom Busy Content
description: Check our &quot;Custom Busy Content&quot; documentation article for Telerik BusyIndicator for .NET MAUI.
position: 2
slug: busyindicator-custom-busy-content
---

#  Custom Busy Content

Setting `BusyContent` property of RadBusyIndicator allows you to display any content together with the built-in animations while the control is in Busy state. Additionally, you can customize the `BusyContentTemplate` in order to arrange the custom content and the animated content per your choice.

Here is a quick example demonstrating how to apply `BusyContent` and `BusyContentTemplate` properties.

<snippet id='busyindicator-custombusycontent-xaml' />
```XAML
<telerikPrimitives:RadBusyIndicator x:Name="BusyIndicator"
									AnimationContentHeightRequest="100"
									AnimationContentWidthRequest="100"  
									AnimationType="Animation6"                                            
									IsBusy="True">           
    <telerikPrimitives:RadBusyIndicator.BusyContent>
        <Label Text="Working on it, just a moment, please..." />
    </telerikPrimitives:RadBusyIndicator.BusyContent>
    <telerikPrimitives:RadBusyIndicator.BusyContentTemplate>
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
    </telerikPrimitives:RadBusyIndicator.BusyContentTemplate>
</telerikPrimitives:RadBusyIndicator>
```

Also you will need to add the **telerikPrimitives** namespace:

<snippet id='xmlns-telerikprimitives' />
```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
```

Check the result in the image below:

![BusyIndicator example](images/busyindicator-custombusycontent.png)

## See Also

- [Animations]({% slug busyindicator-animations %})