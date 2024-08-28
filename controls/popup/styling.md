---
title: Styling
page_title: .NET MAUI Popup Documentation - Styling
description: Style the appearance of the Telerik UI for .NET MAUI Popup by setting its overlay color.
position: 10
slug: popup-styling
---

# .NET MAUI Popup Styling

The `OutsideBackgroundColor` property of the [.NET MAUI Popup]({%slug popup-overview%}) lets you customize the color outside the element.

In most cases, this feature is used for modal popups to indicate that the user cannot interact with the UI behind. The default value is `Color.Transparent`.

You can apply the transparency of the overlay through the alpha channel of the chosen color. If you're using a hexadecimal code, its format has to be `#AARRGGBB`, where the first pair of letters, the `AA`, represents the alpha channel.

Below is an example on how to apply `OutsideBackgroundColor` to a modal popup.

<snippet id='popup-styling' />

Set the needed event handlers that are used to show or hide the popup:

<snippet id='popup-styling-events' />

The following image shows a Popup with an applied overlay color:

![.NET MAUI Popup Modal](images/popup_features_modal.png)

## See Also

- [Modal Popup]({% slug popup-modal %})
