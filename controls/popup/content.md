---
title: Content
page_title: .NET MAUI Popup Documentation | Content
description: "Set the content of the Telerik UI for .NET MAUI Popup and determine when it will open or close."
position: 2
slug: popup-content
---

# Content

The Popup provides options for setting its content and for defining when it will open and close.

## Opening and Closing

To show the Popup control, set `IsOpen` property to `True`. By default, the Popup stays open until the `IsOpen` property is set to `False` or, in case of a non-modal Popup, until the user clicks outside the control.

## Setting the Content

To host content inside the Popup, either add it directly as a child element or use the `ContentTemplate` Popup property.

The example below demonstrates how to create a sample `DataTemplate` and set it as the `ContentTemplate` of the Popup.

1. Add the needed `DataTemplate` to the page Resources:

```XAML
<ResourceDictionary>
    <DataTemplate x:Key="PopupTemplate">
        <telerikMauiControls:RadBorder CornerRadius="8"
                                     BackgroundColor="#93D7FF"
                                     WidthRequest="250"
                                     Padding="10">
            <Grid WidthRequest="250"
				  HeightRequest="150">
                <Grid.RowDefinitions>
                    <RowDefinition Height="30" />
                    <RowDefinition Height="50" />
                    <RowDefinition Height="30" />
                </Grid.RowDefinitions>
                <Label Text="ACCEPT TERMS" />
                <Label Grid.Row="1"
                       Text="By checking this, you agree to the Terms of Service and Privacy Policy." />
                <Button Grid.Row="2"
                        Padding="2"
                        HorizontalOptions="Start"
                        Text="Agree &amp; Continue"
                        Clicked="ClosePopup"
                        CornerRadius="6"
                        BackgroundColor="#7A9BFF"
                        TextColor="White"/>
            </Grid>
        </telerikMauiControls:RadBorder>
    </DataTemplate>
</ResourceDictionary>
 ```

1. When you define the Popup either in XAML or as code-behind, apply the `ContentTemplate` property:

 ```XAML
<StackLayout Orientation="Horizontal" VerticalOptions="Start">
    <telerikPrimitives:RadCheckBox x:Name="checkbox"
                                   IsCheckedChanged="Checkbox_IsCheckedChanged">
        <telerikPrimitives:RadPopup.Popup>
            <telerikPrimitives:RadPopup x:Name="popup"
                                        Placement="Bottom"
                                        ContentTemplate="{StaticResource PopupTemplate}" />
        </telerikPrimitives:RadPopup.Popup>
    </telerikPrimitives:RadCheckBox>
    <Label Text="Agree to the Terms &amp; Conditions"/>
</StackLayout>
 ```

1. Add the events as shown below:

 ```C#
private void ClosePopup(object sender, EventArgs e)
{
    popup.IsOpen = false;
}
private void Checkbox_IsCheckedChanged(object sender, IsCheckedChangedEventArgs e)
{
    if (e.NewValue == true)
        popup.IsOpen = true;
}
 ```


The following image shows the end result.

![Popup Content Template](images/popup_features_contenttemplate.png)

## See Also

- [Modal Popup]({% slug popup-modal %})
