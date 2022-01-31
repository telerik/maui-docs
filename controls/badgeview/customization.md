---
title: Customization
page_title: .NET MAUI BadgeView Documentation | Customizatin
description: Check our &quot;Badge Customization&quot; documentation article for Telerik BadgeView for .NET MAUI.
position: 9
slug: badgeview-customization
---

# Customization

If you don't want to use a [predefined Badge type]({%slug badgeview-predefined-badges%}) and need to customize the text inside the Badge indicator, use the `BadgeText`(`string`) property.

```XAML
<telerikPrimitives:RadBadgeView BadgeText="Badge Text">
    <telerikPrimitives:RadBadgeView.Content>
        <telerikPrimitives:RadBorder WidthRequest="80"
                                     HeightRequest="80"
                                     BorderThickness="1"
                                     BorderColor="LightGray">
            <Label Text="Telerik Badge View for MAUI"
                   FontSize="14"
                   VerticalTextAlignment="Center"
                   HorizontalTextAlignment="Center"/>
        </telerikPrimitives:RadBorder>
    </telerikPrimitives:RadBadgeView.Content>
</telerikPrimitives:RadBadgeView>
```

The following image shows the final result.

![BadgeView Badge Text](images/badgeview-badgetext.png)

## ControlTemplate

The BadgeView supports a default `ControlTemplate` which you can customize.

>important To override the default control template, you need to set an implicit style with `TargetType="telerikPrimitives:Badge"`.

### Use the Default ControlTemplate

To use the default `ControlTemplate`:

1. Set the default `ControlTemplate` in the page resources:

 <snippet id='badgeview-badge-control-template'/>

1. The following snippet shows the BadgeView definition in XAML:

 <snippet id='badgeview-controltemplate'/>

1. Add the following namespace:

 ```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
 ```

The following image shows the final result.

![Badge Default control Template](images/badgeview-default-controltemplate.png)

### Use a Custom ControlTemplate

To customize the `ControlTemplate`:

1. Define the custom `ControlTemplate` in the page resources:

 <snippet id='badgeview-badge-custom-control-template'/>

1. The following snippet shows the BadgeView definition in XAML:

 <snippet id='badgeview-custom-controltemplate'/>

1. Add the following namespace:

 ```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
 ```

The following image shows the final result.

![Badge Custom Control Template](images/badgeview-custom-controltemplate.png)

>important For a BadgeView ControlTemplate example, go to the `FeaturesCategory` folder in [`SDKBrowserMaui Demo Application/Examples/BadgeViewControl`](%slug maui-demo-app%}).

## See Also

- [Badge Position and Alignment]({%slug badgeview-position-alignment%})
- [Badge Animation]({%slug badgeview-animation%})
- [Badge Types]({%slug badgeview-predefined-badges%})
