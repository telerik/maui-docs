---
title: Placement
page_title: .NET MAUI Popup Documentation | Placement
description: "Set the position of the Telerik UI for .NET MAUI Popup to the top, right, left, or bottom of the screen, center it or locate it in relation to another UI element."
position: 5
slug: popup-placement
---

# Placement

The Popup supports useful properties, which enable you to position it depending on your requirements.

* `PlacementTarget`&mdash;Defines an element in relation to which the popup is positioned when it is open.

* `Placement`&mdash;Specifies the way the popup aligns to its placement target. The `Placement` property is of type `PlacementMode` and can be set to any of the `Top`, `Right`, `Left`, `Bottom`, `Center`, or `Relative` options where:
	* `Top`, `Right`, `Left`, and `Bottom` align the Popup control to the corresponding corner of the placement target.
	* `Center` aligns the Popup at the middle of the `PlacementTarget`.
	* `Relative` indicates a position that aligns the top left corner of the Popup with the top left corner of the placement target.

* `HorizontalOffset` and `VerticalOffset` specify the horizontal or vertical distance between the placement target and the alignment point.  

In the following XAML example, the Popup is defined inline through the attached `RadPopup.Popup` property that is applied to the Button control, so that the Button is considered a `PlacementTarget` for the Popup. If you create the Popup with code, you have to explicitly set the `PlacementTarget` property.

When the Popup is declared in XAML and you want to center it, attach it to the `Page` element and set its `Placement` property to `"Center"`.

```XAML
<Button HorizontalOptions="Center"
        VerticalOptions="Start"
        BackgroundColor="#7A9BFF"
        TextColor="White"
        Text="Show popup"
        Clicked="ShowPopup"
        x:Name="button">
    <telerikPrimitives:RadPopup.Popup>
        <telerikPrimitives:RadPopup x:Name="popup"
                                    Placement="Bottom"
                                    HorizontalOffset="20"
                                    VerticalOffset="20">
            <telerikMauiControls:RadBorder
                WidthRequest="180"
                CornerRadius="6"
                BackgroundColor="#93D7FF"
                BorderColor="#7A9BFF"
                Padding="10">
                <Label  WidthRequest="160"
						HeightRequest="200"
						LineBreakMode="WordWrap"
						Text="With Telerik Popup for .NET MAUI you can easily add modal popups to your application to draw attention to important information or receive user input." />
            </telerikMauiControls:RadBorder>
        </telerikPrimitives:RadPopup>
    </telerikPrimitives:RadPopup.Popup>
</Button>
```

Here is the Button `Clicked` event handler:

```C#
private void ShowPopup(object sender, EventArgs e)
{
    popup.IsOpen = true;
}
```

The following image shows the end result.

![Popup Placement](images/popup_features_placement.png)

## See Also

- [Getting Started with Telerik UI for .NET MAUI Popup]({% slug popup-getting-started %})
