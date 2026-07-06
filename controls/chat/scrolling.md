---
title: Scrolling
page_title: .NET MAUI Chat Documentation - Scrolling
description: Learn how to control automatic and programmatic scrolling in the Telerik UI for .NET MAUI Chat control.
position: 9
slug: chat-scrolling
---

# .NET MAUI Chat Scrolling

The Telerik UI for .NET MAUI Chat exposes API that lets you control how the conversation view scrolls when messages are added and how to navigate to a specific item programmatically.

## Auto Scroll

Use the `AutoScrollMode` (`AutoScrollMode`) property to control whether the Chat scrolls automatically when messages are sent or received.

The property supports the following values:

* `Automatic`&mdash;Applies the default behavior. The Chat scrolls automatically when the current user sends a message and when new items are received only if the list is already scrolled to the bottom.
* `Always`&mdash;Scrolls to the new message whenever a message is sent or received, regardless of the current scroll position.
* `Never`&mdash;Disables automatic scrolling. Use this mode when you need to preserve the current scroll position while appending older or incoming messages.

## Scroll to Item

Use the `ScrollTo(int index)` method to scroll the conversation to a specific item by index.

The following example scrolls to the last item in the Chat:

```C#
var lastIndex = this.chat.Items.Count - 1;
if (lastIndex >= 0)
{
    this.chat.ScrollTo(lastIndex);
}
```

## See Also

- [Overview]({%slug chat-overview%})
- [Methods]({%slug chat-methods%})
- [Commands]({%slug chat-commands%})