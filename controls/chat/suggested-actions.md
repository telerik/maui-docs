---
title: Suggested Actions
page_title: .NET MAUI Conversational UI Documentation - Suggested Actions
description: Learn more about suggested actions functionality of the RadChat
position: 8
slug: chat-suggested-actions
---

# .NET MAUI Chat Suggested Actions

The `RadChat` control enables you to add suggestions for the users. You can achieve this by adding `SuggestedActionsItem` instances to the `Items` collection of `RadChat`.

### Adding the Suggested Actions 

The following example demonstrates how to create and set up a `SuggestedActionsItem`:

<snippet id='chat-suggested-actions-code' />

Then, the `GetSuggestedActions` method populates the `Actions` property with a collection of `SuggestedAction` items:

<snippet id='chat-suggested-actions-collection' />

>caption `RadChat` with suggested actions

![.NET MAUI Chat with suggested actions](images/chat-suggested-actions.png)

## See Also

- [Commands]({% slug chat-commands %})