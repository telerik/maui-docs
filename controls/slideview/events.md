---
title: Events 
page_title: .NET MAUI SlideView Documentation - Events
description: Review the different events that are triggered on when the current item is changed.
position: 11
slug: slideview-events
---

# .NET MAUI SlideView Events 

When the current item or its index changes, the SlideView control emits the `CurrentItemChanged` event. You can handle the event and customize the behavior of the component.

## Example

To handle the `CurrentItemChanged` event of `RadSlideView`:

**1.** Add the `RadSlideView` definition.

<snippet id='slideview-events' />

**2.** Add the event handler.

<snippet id='slideview-events-current-item-changed-event' />

> For a runnable example with the SlideView Events scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **SlideView > Events**.

## See Also

- [Using Navigation Buttons in SlideView]({%slug slideview-interaction%})
- [Executing Commands on Slide Action]({%slug slideview-commands%})
- [Using an Item Template in SlideView]({%slug slideview-item-template%})
- [Styling the SlideView Component]({%slug slideview-navigation-buttons-styling%})
- [Styling the SlideView Indicators]({%slug indicators-styling%})