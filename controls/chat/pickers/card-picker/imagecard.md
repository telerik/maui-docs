---
title: ImageCard
page_title: .NET MAUI Conversational UI Documentation - Chat ImageCardContext
description: Learn more about ImageCard functionality of the RadChat control
position: 1
slug: chat-imagecard
---

# `ImageCard` 

`ImageCardContext` enhances the functionality of the `BasicCardContext` by providing an additional `Image` property, so you can add an image to the Card definition. 

Here is a quick example on how to create a sequence of Image Cards and show it through the `RadChatPicker` control.

```C#
var cardsContext = new CardPickerContext {
Cards = new List<CardContext>()
{
	new ImageCardContext() {
		Title ="Rome",
		Subtitle ="Italy",
		Description ="Italy’s capital is one of the world’s most romantic and inspiring cities",
		Image = "RomeCard.png"
	},
	new ImageCardContext() {
		Title ="Barcelona",
		Subtitle ="Spain",
		Description ="Barcelona is an enchanting seaside city with remarkable architecture",
		Image = "BarcelonaCard.png"
	}}
};
(chat.Picker as RadChatPicker).Context = cardsContext;
```
	
## See Also

- [ChatPicker]({% slug chat-picker-overview %})
- [BasicCard] ({% slug chat-cardpicker %})