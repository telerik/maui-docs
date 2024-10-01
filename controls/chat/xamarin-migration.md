---
title: Migrating from Xamarin
page_title: .NET MAUI Conversational UI Documentation - Migrate from Xamarin
description: Learn how to migrate from the Xamarin.Forms RadChat to the .NET MAUI Chat control.
position: 100
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
previous_url: /controls/chat/migrate-from-xamarin
slug: chat-migrate-from-xamarin
---

# Migrating from Xamarin.Forms Chat to .NET MAUI Chat

The Telerik UI for .NET MAUI Chat preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

The tables in the following sections list any differences between the APIs of the Xamarin.Forms Chat and .NET MAUI Chat.

## Migrate Namespaces

| Control | Control name | XAML Namespace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin Chat | `RadChat` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.ConversationalUI;assembly=Telerik.XamarinForms.ConversationalUI" | using Telerik.XamarinForms.ConversationalUI; | 
| .NET MAUI Chat | `RadChat` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |


## API Changes

| Xamarin RadChat | .NET MAUI RadChat |
| ------------- | --------------- |
| N/A | `SuggestedActionsItem` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
* [.NET MAUI Chat Product Page](https://www.telerik.com/maui-ui/chat-(conversational-ui))
* [.NET MAUI Chat Forum Page](https://www.telerik.com/forums/maui?tagId=2061)
