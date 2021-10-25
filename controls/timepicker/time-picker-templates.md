---
title: Templates
page_title: .NET MAUI Time Picker Documentation | Templates
description: Check our &quot;Templates&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 3
slug: time-picker-templates
---

# Templates

In case the default templates of the TimePicker control do not suit your needs, you can easily define a custom template. The available templates for customizing are:

* **PlaceholderTemplate**(*ControlTemplate*): Defines the template visualized for the placeholder.  
* **DisplayTemplate**(*ControlTemplate*): Defines the template visualized when the picked time is displayed.
* **HeaderTemplate**(*ControlTemplate*): Defines what will be displayed inside the dialog(popup) header.
* **FooterTemplate**(*ControlTemplate*): Defines what will be displayed inside the dialog(popup) footer.

The snippet below shows a sample RadTimePicker definition with the listed above template properties applied:

1. RadTimePicker definition:

```XAML
<telerikInput:RadTimePicker SpinnerFormat="H:mm"
                            PlaceholderTemplate="{StaticResource placeholderTemplate}"
                            DisplayTemplate="{StaticResource displayTemplate}">
    <telerikInput:RadTimePicker.SelectorSettings>
        <telerikInput:PickerPopupSelectorSettings HeaderTemplate="{StaticResource headerTemplate}"
                                                  FooterTemplate="{StaticResource footerTemplate}"/>
    </telerikInput:RadTimePicker.SelectorSettings>
</telerikInput:RadTimePicker>
```

1. Add the following namespace:

 ```XAML
 xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```
 
For the example the templates definition are added to the page's resources:

## PlaceholderTemplate

```XAML
<ControlTemplate x:Key="placeholderTemplate">
    <Button Text="Pick a time" 
            FontAttributes="Bold" 
            TextColor="White"
            BackgroundColor="#B73562" 
            HeightRequest="50" Command="{TemplateBinding ToggleCommand}" />
</ControlTemplate>
```

![RadTimePicker PlaceholderTemplate](images/timepicker_placeholder_template.png)

## DisplayTemplate

```XAML
<ControlTemplate x:Key="displayTemplate">
    <Button Text="{TemplateBinding DisplayString}" 
            TextColor="White" 
            BackgroundColor="#7BAEFF"
            HeightRequest="50"
            Command="{TemplateBinding ToggleCommand}" />
</ControlTemplate>
```

![RadTimePicker DisplayTemplate](images/timepicker_display_template.png)

## HeaderTemplate

```XAML
<ControlTemplate x:Key="headerTemplate">
    <Label Text="Time Picker" 
           TextColor="White"
           VerticalTextAlignment="Center"
           HorizontalTextAlignment="Center"
           BackgroundColor="#B73562"/>
</ControlTemplate>
```

## FooterTemplate

```XAML
<ControlTemplate x:Key="footerTemplate">
    <StackLayout Orientation="Horizontal" Spacing="0" HorizontalOptions="FillAndExpand" BackgroundColor="#B73562">
        <Button Text="No" 
                TextColor="White"
                BackgroundColor="Transparent"
                Command="{TemplateBinding CancelCommand}" />
        <Button Text="Yes"
                TextColor="White"
                BackgroundColor="Transparent"
                Command="{TemplateBinding AcceptCommand}" />
    </StackLayout>
</ControlTemplate>
```

![RadTimePicker FooterTemplate](images/timepicker_header_footer_template.png)


## See Also

- [Suppoted Standard Time Format Strings]({%slug time-picker-formatting%})
- [Styling]({%slug time-picker-styling%})