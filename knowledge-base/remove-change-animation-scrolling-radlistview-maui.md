---
title: How to Remove or Change the Animation When Scrolling through a RadListView for MAUI
description: This article explains how to disable or customize the animation that occurs when scrolling through a RadListView in ListView for MAUI.
type: how-to
page_title: Remove or Change Animation When Scrolling through RadListView | ListView for MAUI
slug: remove-change-animation-scrolling-radlistview-maui
tags: maui, radlistview, animation, scrolling, customization
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.6.0 | Telerik UI for .NET MAUI ListView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

When scrolling through a RadListView for MAUI, an animation occurs for each list view cell. This animation can be distracting and inconsistent, as it only happens for the top items in the list view. This article explains how to disable or customize this animation to achieve a more subtle scrolling experience.

## Solution

To remove or change the animation when scrolling through a RadListView you can follow these steps:

**1.** Check the native implementation for Android and iOS ListView animations:
   - Android ListView animations: [https://docs.telerik.com/devtools/xamarin/nativecontrols/android/listview/listview-itemanimations](https://docs.telerik.com/devtools/xamarin/nativecontrols/android/listview/listview-itemanimations)
   - iOS ListView animations: [https://docs.telerik.com/devtools/xamarin/nativecontrols/ios/listview/animations](https://docs.telerik.com/devtools/xamarin/nativecontrols/ios/listview/animations)

**2.** Subscribe to the `HandlerChanged` event of the RadListView control in your XAML file:
```xml
<telerik:RadListView ItemsSource="{Binding Source}" HandlerChanged="listView_HandlerChanged" x:Name="listView" />
```

**3.** Implement the event handler in your code-behind file to customize the animations:

```C#
private void listView_HandlerChanged(object sender, EventArgs e)
{
    if (this.listView.Handler == null) return;

#if ANDROID
    Com.Telerik.Widget.List.FadeItemAnimator fadeItemAnimator = new Com.Telerik.Widget.List.FadeItemAnimator();
    var platform = (Android.Widget.FrameLayout)this.listView.Handler.PlatformView;
    Telerik.Maui.Controls.Compatibility.DataControlsRenderer.Android.ListView.RadListViewWrapper wrapper = (Telerik.Maui.Controls.Compatibility.DataControlsRenderer.Android.ListView.RadListViewWrapper)platform;
    wrapper.ListView.SetItemAnimator(fadeItemAnimator);

#elif IOS17_0_OR_GREATER

        var platformList = (TelerikUI.TKListView)this.listView.Handler.PlatformView;
    TelerikUI.TKListViewLinearLayout layout = (TelerikUI.TKListViewLinearLayout)platformList.Layout;
    layout.AnimationDuration = 0;
#endif
}
```

**4.** Build and run your application to see the updated scrolling behavior of the RadListView.

## Notes

- Disabling or customizing the animation when scrolling through a RadListView requires using the native implementations for Android and iOS ListView control.

## See Also

- [Android ListView animations](https://docs.telerik.com/devtools/xamarin/nativecontrols/android/listview/listview-itemanimations)
- [iOS ListView animations](https://docs.telerik.com/devtools/xamarin/nativecontrols/ios/listview/animations)
