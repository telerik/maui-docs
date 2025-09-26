---
title: Setting Focus on Entry Using MVVM in UI for .NET MAUI
description: Learn how to set focus on an Entry control when it loads using the MVVM approach in UI for .NET MAUI.
type: how-to
page_title: How to Set Focus on Entry Control in UI for .NET MAUI Using MVVM
meta_title: Focus Entry Control Using MVVM in UI for .NET MAUI
slug: set-focus-entry-mvvm-ui-net-maui
tags: entry, mvvm, telerik ui for .net maui, entry focus, eventtocommandbehavior, radeventtocommandbehavior
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI Entry | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to set focus on an Entry control when the page loads using the MVVM (Model-View-ViewModel) approach in UI for .NET MAUI.

This knowledge base article also answers the following questions:
- How to use `EventToCommandBehavior` for Entry focus in .NET MAUI?
- How to use `RadEventToCommandBehavior` for Entry focus in .NET MAUI?
- How to set Entry focus programmatically using MVVM?

## Solution

To achieve this, use either the `EventToCommandBehavior` from CommunityToolkit or `RadEventToCommandBehavior` from Telerik UI for .NET MAUI.

### Approach 1: Using `RadEventToCommandBehavior`

This approach doesn't require explicitly setting the `BindingContext` inside the event to command behavior.

1. Add the behavior to the Entry control:

   ```xaml
   <te:RadEntry.Behaviors>
       <te:RadEventToCommandBehavior
               EventName="Loaded"
               Command="{Binding EntryLoadedCommand}"
               CommandParameter="{Binding Source={x:Reference Entry}}" />
   </te:RadEntry.Behaviors>
   ```

2. Create a command in your ViewModel:

   ```csharp
   [RelayCommand]
   async Task EntryLoaded(object sender)
   {
       if (sender is Telerik.Maui.Controls.RadEntry entry)
       {
           await MainThread.InvokeOnMainThreadAsync(() => entry.Focus());
       }
   }
   ```

### Approach 2: Using `EventToCommandBehavior` from CommunityToolkit

1. Explicitly set the behavior's `BindingContext` to the page's ViewModel:

   ```xaml
   <te:RadEntry.Behaviors>
       <toolkit:EventToCommandBehavior
           EventName="Loaded"
           Command="{Binding EntryLoadedCommand}"
           CommandParameter="{Binding Source={x:Reference Entry}}"
           BindingContext="{Binding Source={x:Reference MainPage}, Path=BindingContext}" />
   </te:RadEntry.Behaviors>
   ```

2. Add a name to the ContentPage:

   ```xaml
   <ContentPage x:Name="MainPage" ...>
   ```

3. Define the command in your ViewModel:

   ```csharp
   [RelayCommand]
   async Task EntryLoaded(object sender)
   {
       if (sender is Telerik.Maui.Controls.RadEntry entry)
       {
           await MainThread.InvokeOnMainThreadAsync(() => entry.Focus());
       }
   }
   ```

Both approaches achieve the desired behavior of setting focus on the Entry control when it loads.

## See Also

- [UI for .NET MAUI Entry Documentation](https://docs.telerik.com/devtools/maui/controls/entry/overview)
- [RadEventToCommandBehavior Documentation](https://docs.telerik.com/devtools/maui/api/telerik.maui.controls.radeventtocommandbehavior)
- [CommunityToolkit EventToCommandBehavior Documentation](https://learn.microsoft.com/en-us/dotnet/communitytoolkit/maui/behaviors/event-to-command-behavior)
