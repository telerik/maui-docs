---
title: Suggested Actions
page_title: .NET MAUI Conversational UI Documentation - Suggested Actions
description: Learn more about suggested actions functionality of the RadChat
position: 8
slug: chat-suggested-actions
---

# .NET MAUI Chat Suggested Actions

`RadChat` supports adding suggestions to the user. This can be done by adding `SuggestedActionsItem` instances to the `Items` collection of `RadChat`.

### Adding the Suggested Actions 

The following example demonstrates how to create and setup a SuggestedActionsItem:

<snippet id='chat-suggested-actions-code' />

The `GetSuggestedActions` method then populates the `Actions` property with a collection of `SuggestedAction` items:

<snippet id='chat-suggested-actions-collection' />

#### Figure 1: RadChat with suggested actions

![RadChat with suggested actions](images/)

## See Also

- [Commands]({% slug chat-commands %})