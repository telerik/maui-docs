---
title: Overview
page_title: .NET MAUI Conversational UI Documentation - Chat CardPicker
description: Learn more about CardPicker and how to use it on RadChatPicker control
position: 0
slug: chat-cardpicker
---

# CardPicker Overview

`RadChatPicker` control provides a `CardPickerContext` that can be used to display a list of cards. Each card presents more complex information in a user-friendly structured manner and allows the user to interact with it. 

`CardPickerContext` exposes the following property:

* `Cards`&mdash;It is of type IEnumerable&lt;CardContext&gt; and contains the available Cards defined by the CardContext;

Depending on the information that is presented, the `CardContext` can be one of the following types:

* `BasicCardContext`&mdash;For displaying a card with `Title`, `SubTitle` and `Description`;
* `ImageCardContext`&mdash;Derives from BasicCardContext with an additional Image property;

Here is a quick example with BasicCardContext:

<snippet id='chat-chatpicker-cardpicker-pickeritem' />

And the used `GetCards()` method:

```C#
private IEnumerable<CardContext> GetCards(ChatItem chatItem)
{
	List<CardContext> cards = new List<CardContext>()
	{
		new BasicCardContext() {Title="Rome", Subtitle="Italy", Description="Italy’s capital is one of the world’s most romantic and inspiring cities"},
		new BasicCardContext() {Title="Barcelona", Subtitle="Spain", Description="Barcelona is an enchanting seaside city with remarkable architecture"}
	};
	return cards;
}
```
	
#### Figure 1: RadChat with BasicCard

![CardPicker](images/)
	
#### Card Actions

Each card allows you to add a certain action that can be handled through a command. The `CardContext` exposes an `Actions` collection of type IEnumerable&lt;CardActionContext&gt; that supplies all the details needed for handling the action.

`CardActionContext` provides the following properties:

* `Text`&mdash;Represents the action inside the Card layout;
* `Command`&mdash;The command that is raised when the user selects that action;
* `Data`&mdash;Can be used to preserve additional details if needed;

The next snippet uses the Cards defined in the previous example and adds Actions to them.

<snippet id='chat-chatpicker-cardpicker-getcards' />

#### Figure 2: RadChat with BasicCard with Actions

![CardPicker](images/)

## See Also

- [ChatPicker]({% slug chat-picker-overview %})
- [ImageCard]({% slug chat-imagecard %})