---
title: Modal Popup
page_title: .NET MAUI Popup Documentation - Modal Popup
description: Determine whether the Telerik UI for .NET MAUI Popup will be rendered as a modal or non-modal UI element.
position: 3
slug: popup-modal
---

# .NET MAUI Modal Popup

You can define whether the [.NET MAUI Popup]({%slug popup-overview%}) will be modal or not through the `IsModal` Boolean property. In both cases, the UI behind the popup gets inactive and cannot be used until the popup is closed. For non-modal popups, however, you can focus the content behind by clicking outside the popup, thus closing it.

Here is an example of a modal popup attached to the `ContentPage`:

<snippet id='popup-features-modal' />

And the next example shows the event handlers for opening/closing the popup:

<snippet id='popup-features-modal-events' />

Here is the result&mdash;the Popup applies the default outside background color for the content behind:

![.NET MAUI Popup Modal](images/popup-modal.png)

## See Also

- [Popup Content]({% slug popup-content %})
- [Styling]({% slug popup-styling %})