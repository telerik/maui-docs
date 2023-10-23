---
title: Commands
page_title: .NET MAUI NavigationView Documentation - Commands
description: The .NET MAUI NavigationView provides commands that allow you to initiate open or close actions for the pane.
position: 12
slug: navigationview-commands
---

# .NET MAUI NavigationView Commands

The .NET MAUI NavigationView provides commands that allow you to initiate open or close actions for the pane and toggle its state. 

The available commands are:

* `OpenPaneCommand` (`ICommand`)&mdash;Gets the command which opens the pane.
* `ClosePaneCommand` (`ICommand`)&mdash;Gets the command which closes the pane.
* `TogglePaneCommand` (`ICommand`)&mdash;Gets the command which opens and closes the pane.

Here is an example how to use the commands:

**1.**  Bind the NavigationView commands to buttons command:

```XAML
<HorizontalStackLayout Spacing="5">
    <Button Text="Open Pane" Command="{Binding OpenPaneCommand, Source={x:Reference navigationView}}"/>
    <Button Text="Close Pane" Command="{Binding ClosePaneCommand, Source={x:Reference navigationView}}"/>
    <Button Text="Toggle Pane" Command="{Binding TogglePaneCommand, Source={x:Reference navigationView}}"/>
</HorizontalStackLayout>
```

**2.**  Define the NavigationView control:

<snippet id='navigationview-commands' />

**3.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [.NET MAUI NavigationView Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
