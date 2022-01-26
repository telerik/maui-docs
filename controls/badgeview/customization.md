---
title: Badge Customization
page_title: .NET MAUI BadgeView Documentation | BadgeView Customizatin
description: Check our &quot;Badge Customization&quot; documentation article for Telerik BadgeView for .NET MAUI.
position: 10
slug: badgeview-customization
---

# Badge Customization

Customize the text inside the badge using the `BadgeText`(`string`) property, in case you don't want to use one of the [predefined badges]({%slug badgeview-predefined-badges%}). 

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

The final result:

![BadgeView Badge Text](images/badgeview-badgetext.png)

## Badge ControlTemplate

The Badge has a default ControlTemplate which you can customize. 

>important In order to override the default control template you will need to set implicit style with `TargetType="telerikPrimitives:Badge"`

### Default ControlTemplate

![Badge Default control Template](images/badgeview-default-controltemplate.png)

Default ControlTemplate defined in the page's resources:

<snippet id='badgeview-badge-control-template'/>

RadBadgeView definition in XAML:

<snippet id='badgeview-controltemplate'/>

Add the following namespace:

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
```

## Custom ControlTemplate

![Badge Custom Control Template](images/badgeview-custom-controltemplate.png)

Custom ControlTemplate defined in the page's resources:

<snippet id='badgeview-badge-custom-control-template'/>

RadBadgeView definition in XAML

<snippet id='badgeview-custom-controltemplate'/>

Add the following namespace:

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
```

>important BadgeView ControlTemplate Example can be found inside the FeaturesCategory folder in [SDKBrowserMaui Demo Application/Examples/BadgeViewControl](%slug maui-demo-app%}).

## See Also

- [Badge Position and Alignment]({%slug badgeview-position-alignment%})
- [Badge Animation]({%slug badgeview-animation%})
- [Badge Types]({%slug badgeview-predefined-badges%})