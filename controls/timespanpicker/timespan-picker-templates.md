---
title: Templates
page_title: .NET MAUI TimeSpan Picker Documentation | Templates
description: Check our &quot;Templates&quot; documentation article for Telerik TimeSpan Picker for .NET MAUI.
position: 4
slug: timespan-picker-templates
---

# Templates

If the default templates of the control do not suit your needs, you can easily define custom ones. The available templates for customizing are:

* `PlaceholderTemplate`(*ControlTemplate*): Defines the template visualized for the placeholder.  
* `DisplayTemplate`(*ControlTemplate*): Defines the template visualized when the picked date/time is displayed.
* `HeaderTemplate`(*ControlTemplate*): Defines what will be displayed inside the dialog(popup) header.
* `FooterTemplate`(*ControlTemplate*): Defines what will be displayed inside the dialog(popup) footer.

## PlaceholderTemplate

```XAML
<ControlTemplate x:Key="placeholderTemplate">
    <Button Text="Pick a time interval" 
            FontAttributes="Bold" 
            TextColor="White"
            BackgroundColor="#70B8FF" 
            HeightRequest="50" 
            Command="{TemplateBinding ToggleCommand}" />
</ControlTemplate>
```

## DisplayTemplate

```XAML
 <ControlTemplate x:Key="displayTemplate">
    <Button Text="{TemplateBinding DisplayString}" 
            TextColor="White" 
            BackgroundColor="#70B8FF"
            HeightRequest="50"
            Command="{TemplateBinding ToggleCommand}" />
</ControlTemplate>
```

## HeaderTemplate

```XAML
 <ControlTemplate x:Key="headerTemplate">
    <Label Text="Select Duration" 
           TextColor="White"
           VerticalTextAlignment="Center"
           HorizontalTextAlignment="Center"
           BackgroundColor="#70B8FF"/>
</ControlTemplate>
```

## FooterTemplate

```XAML
<ControlTemplate x:Key="footerTemplate">
    <StackLayout Orientation="Horizontal" Spacing="0" HorizontalOptions="FillAndExpand" BackgroundColor="#70B8FF">
        <Button Text="&#xE80A;"
                FontFamily="TelerikFontExamples"
                TextColor="White"
                BackgroundColor="Transparent"
                Command="{TemplateBinding CancelCommand}" />
        <Button Text="&#xE809;"
                FontFamily="TelerikFontExamples"
                TextColor="White"
                BackgroundColor="Transparent"
                Command="{TemplateBinding AcceptCommand}" />
    </StackLayout>
</ControlTemplate>
```

and the TimeSpan Picker definition:

```XAML
<telerikInput:RadTimeSpanPicker PlaceholderTemplate="{StaticResource placeholderTemplate}"
                                DisplayTemplate="{StaticResource displayTemplate}">
    <telerikInput:RadTimeSpanPicker.SelectorSettings>
        <telerikInput:PickerPopupSelectorSettings HeaderTemplate="{StaticResource headerTemplate}"
                                                  FooterTemplate="{StaticResource footerTemplate}"/>
    </telerikInput:RadTimeSpanPicker.SelectorSettings>
</telerikInput:RadTimeSpanPicker>
```

## See Also

- [Commands]({% slug timespan-picker-commands%})