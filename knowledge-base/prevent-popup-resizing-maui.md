---
title: Fixing the Size of a Popup in MAUI Applications
description: Learn how to set a fixed size for a Popup in MAUI to prevent resizing when its content changes.
type: how-to
page_title: How to Prevent Popup from Resizing with Content Changes in MAUI
slug: prevent-popup-resizing-maui
tags: maui, popup, fixed-size, content change
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI Popup | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

How do I fix the size of a `RadPopup` after it's rendered for the first time, so that changes in the views within the popup do not change the size of the popup? 

This knowledge base article also answers the following questions:
- How to set a fixed size for `RadPopup` in MAUI?
- How to prevent `RadPopup` from resizing when its content changes?
- How to maintain the size of `RadPopup` despite changes in its content?

## Solution

To set a fixed size for a `RadPopup` and prevent it from resizing when the content changes, follow these steps:

1. Measure the popup content at its first load and assign the result to the content's `WidthRequest` and `HeightRequest` properties. When the popup opens for the first time, measure the content by calling the `Measure` method and passing `double.PositiveInfinity` as width and height constraints. 
2. Assign the measurement results to the content's `WidthRequest` and `HeightRequest` properties to fix its size.
3. Unsubscribe from the `Loaded` event to prevent re-measuring when the content changes.

Below is the XAML definition and the corresponding C# code behind demonstrating how to implement this solution:

**XAML**

```xaml
<ContentPage.Resources>
    <DataTemplate x:Key="Template1">
        <ScrollView>
            <VerticalStackLayout BackgroundColor="LightGray" Spacing="5" Padding="5">
                <Button Text="add item" Clicked="Button1_Clicked" />
                <VerticalStackLayout BackgroundColor="LightBlue">
                    <Label Text="item 0" />
                    <Label Text="item 1" />
                    <Label Text="item 2" />
                    <Label Text="item 3" />
                </VerticalStackLayout>
            </VerticalStackLayout>
        </ScrollView>
    </DataTemplate>
</ContentPage.Resources>

<Grid RowDefinitions="Auto,*, Auto">
    <VerticalStackLayout HorizontalOptions="Center" VerticalOptions="Center">
        <Button x:Name="Button2" Text="open popup with Content" Clicked="Button2_Clicked" />
    </VerticalStackLayout>
</Grid>
```

**Code-Behind**

```csharp
public partial class PopupPage : ContentPage
{
    private RadPopup popup;
    
    public PopupPage()
    {
        InitializeComponent();
    }
    
    private void Button1_Clicked(object sender, System.EventArgs e)
    {
        Element element = (Element)sender;
        Layout parentLayout = (Layout)element.Parent;
        Layout layout = (Layout)parentLayout.Children[1];
        layout.Children.Add(new Label { Text = "item " + layout.Children.Count });
    }

    private void Button2_Clicked(object sender, System.EventArgs e)
    {
        if (this.popup == null)
        {
            this.popup = new RadPopup();
            DataTemplate template = (DataTemplate)this.Resources["Template1"];
            View v = template.CreateContent() as View;
            this.popup.Content = v;
            v.Loaded += this.ViewLoaded;
            this.popup.PlacementTarget = (VisualElement)sender;
            this.popup.Placement = PlacementMode.Top;
        }

        this.popup.IsOpen = true;
    }

    private void ViewLoaded(object sender, System.EventArgs e)
    {
        View v = (View)sender;
        var size = v.Measure(double.PositiveInfinity, double.PositiveInfinity);
        v.WidthRequest = size.Request.Width;
        v.HeightRequest = size.Request.Height;
        v.Loaded -= this.ViewLoaded;
    }
}
```

By following the above steps, the Popup's size will remain fixed even when content changes occur, allowing you to scroll through the added items without resizing the popup.

## See Also

- [Popup Overview](https://docs.devexpress.com/MAUI/DevExpress.Maui.Controls.RadPopup)
