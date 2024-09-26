---
title: Disabling Gesture to Open Drawer in .NET MAUI SideDrawer for WinUI
description: Learn how to configure the RadSideDrawer in .NET MAUI so it can only be opened through a button click on WinUI, disabling the gesture control.
type: how-to
page_title: How to Disable Gesture Opening of RadSideDrawer in .NET MAUI on WinUI
slug: disable-gesture-open-sidedrawer-net-maui-winui
tags: sidedrawer, .net maui, winui, gesture, open, button
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 | Telerik UI for .NET MAUI SideDrawer| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

In a .NET MAUI application, you might want to restrict the [SideDrawer]({%slug sidedrawer-overview%}) to open only through a button click, especially on the WinUI platform, instead of using the swipe/drag gesture. This can be essential for cases where gesture control needs to be disabled for specific UI requirements.

This KB article also answers the following questions:
- How can I disable swipe gesture for opening the SideDrawer on WinUI?
- Is it possible to control the SideDrawer's open and close behavior only through a button in .NET MAUI?
- Can I restrict the closing mechanism of the SideDrawer to non-gesture methods in WinUI?

## Solution

To disable the gesture for closing the SideDrawer and make it close only via a button click on WinUI, you will need to use the native control customization options available for the SideDrawer. Specifically, you should set the `DrawerManipulationMode` property to `Button`. This ensures that the drawer does not respond to swipe gestures and only opens when a button is clicked.

Here is the code snippet to achieve this:

```csharp
private void drawer_HandlerChanged(object sender, EventArgs e)
{
    var platformView = this.drawer.Handler.PlatformView;

#if WINDOWS
    var platformdrawer = (Telerik.UI.Xaml.Controls.Primitives.RadSideDrawer)platformView;
    platformdrawer.DrawerManipulationMode = Telerik.UI.Xaml.Controls.Primitives.DrawerManipulationMode.Button;
#endif
}
```

By setting the `DrawerManipulationMode` to `Button`, the SideDrawer on WinUI will ignore swipe gestures and will only allow opening through a button click, thus giving you control over the drawer's behavior.

## See Also

- [RadSideDrawer Overview]({%slug sidedrawer-overview%})
- [Key Properties of RadSideDrawer on WinUI](https://docs.telerik.com/devtools/winui/controls/radsidedrawer/key-properties)
