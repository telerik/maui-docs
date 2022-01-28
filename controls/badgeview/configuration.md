---
title: Configuration
page_title: .NET MAUI BadgeView Documentation | Configuration
description:  "Learn how to define Content, BadgeText, BadgeVisibility and Padding for the Telerik UI for .NET MAUI BadgeView."
position: 2
slug: badgeview-configuration
---

# Configuration

The purpose of this help article is to show you the main configuration options of the BadgeView for .NET MAUI control.

## Content

>important The BadgeView will be visualized only if its `Content` property is set. 

* `Content`(of type `Microsoft.Maui.Controls.View`): Defines the content of the BadgeView.

You must define a content. The Badge marker/indicator is positioned based on the content inside the BadgeView. Without a content the Badge won't be visualized.

```XAML
<telerikPrimitives:RadBadgeView>
    <telerikPrimitives:RadBadgeView.Content>
        <!-- add the content of the RadBadgeView. For exmaple: Label, Image, Frame, Border, Button, etc -->
    </telerikPrimitives:RadBadgeView.Content>
</telerikPrimitives:RadBadgeView>
```

### Example

There is a Button inside the Content. The BadgeText is updated on a ButtonClick.  

<snippet id='badgeview-content'/>

And the page's code behind where is the button click implementation:

<snippet id='badgeview-content-code-behind'/>

And the result

![BadgeView Badge Content](images/badgeview-content-text.gif)

## Badge Text

With `BadgeText` property(`string`) you can define a text. The text will be displayed in the badge marker. 

### Example

```XAML
<telerikPrimitives:RadBadgeView BadgeText="Badge Text">
    <telerikPrimitives:RadBadgeView.Content>
        <telerikPrimitives:RadBorder WidthRequest="80"
                                     HeightRequest="80"
                                     BorderThickness="1"
                                     BorderColor="LightGray">
            <Label Text="Telerik Badge View for Xamarin" 
                   FontSize="14"
                   VerticalTextAlignment="Center"
                   HorizontalTextAlignment="Center"/>
        </telerikPrimitives:RadBorder>
    </telerikPrimitives:RadBadgeView.Content>
</telerikPrimitives:RadBadgeView>
```

![BadgeView Badge Text](images/badgeview-badgetext.png)

>tip You can fully customize the look &amp; feel of the BadgeView, for detailed information check the [Badge Styling]({%slug badgeview-styling%}) and [Badge Customization]({%slug badgeview-customization%}) articles.

## Badge Visibility

Change the Badge visibility state using the `BadgeVisibility` property (enum of type `Telerik.XamarinForms.Common.Visibility`).

The available options are:

* `Visible` - The badge marker/indicator is visualized.
* `Hidden` - The badge marker/indicator is hidden.
* `Collapsed` - The badge marker/indicator is collapsed.

The default value of `BadgeVisibility` is `Visible`.

### Example with BadgeVisibility Hidden

```XAML
<telerikPrimitives:RadBadgeView BadgeText="1" BadgeVisibility="Hidden">
    <telerikPrimitives:RadBadgeView.Content>
        <telerikPrimitives:RadBorder WidthRequest="80"
                                    HeightRequest="80"
                                    BorderThickness="1"
                                    BorderColor="LightGray">
            <Label Text="Telerik Badge View for Xamarin" 
                FontSize="14"
                VerticalTextAlignment="Center"
                HorizontalTextAlignment="Center"/>
        </telerikPrimitives:RadBorder>
    </telerikPrimitives:RadBadgeView.Content>
</telerikPrimitives:RadBadgeView>
```

![BadgeView Badge Visibility](images/badgeview-badge-visibility.png)


## Padding

* `Padding`(`Xamarin.Forms.Thickness`): Defines the inner padding of the BadgeView.

```XAML
 <telerikPrimitives:RadBadgeView BadgeText="Add" Padding="30">
	 <telerikPrimitives:RadBadgeView.Content>
	 <!-- add your content here -->
	 </telerikPrimitives:RadBadgeView.Content>
 </telerikPrimitives:RadBadgeView>
```

![BadgeView Padding](images/badgeview-padding.png)

## See Also

- [Badge Position and Alignment]({%slug badgeview-position-alignment%})
- [Badge Animation]({%slug badgeview-animation%})
- [Badge Types]({%slug badgeview-predefined-badges%})
- [Badge Styling]({%slug badgeview-styling%})
- [Badge Customization]({%slug badgeview-customization%})
