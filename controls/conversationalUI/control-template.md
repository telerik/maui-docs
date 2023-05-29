---
title: Control Template
page_title: .NET MAUI Conversational UI Documentation - Control Template
description: "Learn more about the control template property and how to modify it."
position: 6
slug: chat-control-template
---

# .NET MAUI RadChart Control Template

`RadChart's` visual appearance is defined through a Control Template. In order to customize the way the Conversational UI looks, you would need to take the default `ControlTemplate` and modify it.

This topic gives an overview of the `ControlTemplate` of the Chat control, so you can copy it to your app and make changes.

#### The original ControlTemplate

Here is the RadChat default control template. Add it to the Page resources.

```XAML

```


Finally, use the custom ControlTemplate as a `StaticResource` on any instance of RadChat:

```XAML
<telerik:RadChat x:Name="chat"
				 ControlTemplate="{StaticResource RadChat_ControlTemplate}"/>
```
