---
title: Customizing Chat Item Styles in .NET MAUI
description: Learn how to modify the appearance of chat items, including text color, in the Telerik UI for .NET MAUI Chat component.
type: how-to
page_title: How to Customize Chat Item Styles in Telerik UI for .NET MAUI
slug: customize-chat-item-styles-dotnet-maui
tags: chat, conversational ui, .net maui, styling, text color, item template selector, implicit style
res_type: kb
category: knowledge-base
ticketid: 1652367
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.0.0 | Telerik UI for .NET MAUI Conversational UI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

This KB article answers the following questions:
- How can I change the text color of chat items in .NET MAUI?
- Is there a way to apply custom styles to chat items in .NET MAUI?
- How to use item template selectors for styling chat messages?

## Solution

To customize the style of the chat items in the [Chat]({%slug chat-overview%}) control for .NET MAUI, follow these approaches:

### Approach 1: Using Item Template Selector

Refer to the [Item Template Selector]({%slug chat-itemtemplate-selector%}) documentation. You can change the text color by adding a style targeting the `Label` and setting its `TextColor` property. For example, use a style named `DefaultLabelStyle`. 
See the example code in the <a href="https://github.com/telerik/maui-samples/tree/main/Samples/SdkBrowser/Examples/ChatControl/FeaturesCategory" target="_blank">Telerik MAUI Controls Samples Chat Examples</a>

### Approach 2: Using Implicit Style

Use an implicit style targeting `TextMessageView` or its derived types like `IncomingTextMessageView`, `OutgoingTextMessageView`.

```xml
<Style x:Key="LabelStyle" TargetType="Label">
    <Setter Property="TextColor" Value="Red" />
</Style>
<Style TargetType="telerik:TextMessageView" ApplyToDerivedTypes="True">
    <Setter Property="LabelStyle" Value="{StaticResource LabelStyle}" />
</Style>
```

For further examples, refer to the <a href="https://github.com/telerik/maui-samples/blob/main/Samples/SdkBrowser/Examples/ChatControl/FeaturesCategory/CustomizationExample/Customization.xaml" target="_blank">Telerik MAUI Controls Samples Chat Customization example</a>

## Notes

- The `TextMessageView` and its derived types (`IncomingTextMessageView`, `OutgoingTextMessageView`) are crucial for applying text styles.
- The `LabelStyle` is an example of how to directly modify the `TextColor` property, but you can customize other properties similarly.

## See Also

- [Chat Overview]({%slug chat-overview%})
- [Item Template Selector Documentation]({%slug chat-itemtemplate-selector%})
