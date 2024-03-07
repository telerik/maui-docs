---
title: Making SideDrawer Opacity Consistent across Platforms
description: Learn how to make the opacity of the .NET MAUI SideDrawer consistent across different platforms when the drawer opens.
type: how-to
page_title: How to Implement Consistent SideDrawer Opacity across Platforms in .NET MAUI
slug: make-sidedrawer-opacity-consistent-across-platforms-net-maui
tags: xamarin, .net-maui, sidedrawer, platform-consistency
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | Telerik UI for .NET MAUI SideDrawer | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

I want to make the SideDrawer opacity consistent across different platforms in .NET MAUI. Currently, on iOS, a darkening mask is added over the SideDrawer `MainContent` when the drawer is extended(opened), while on Windows, the `MainContent` appears to brighten. I would like to achieve consistency in this behavior.

## Solution

To achieve consistent behavior for the SideDrawer content across different platforms, you can adjust the fade opacity when the drawer opens. This can be done using the `DrawerTransitionFadeOpacity` property. The fade opacity value ranges from 0 to 1, where 0 represents no opacity and 1 represents full opacity.

Here's an example of how to set the `DrawerTransitionFadeOpacity` property to achieve consistency:

```xaml
<controls:RadSideDrawer x:Name="drawer" 
                         DrawerTransitionType="SlideInOnTop" 
                         DrawerTransitionFadeOpacity="{OnPlatform WinUI=1, iOS=0}"
                         DrawerLength="200">
```

In the above code snippet, the `DrawerTransitionFadeOpacity` property is set to 0 for iOS and 1 for WinUI. This ensures that the darkening mask is not applied on iOS and the `MainContent` appears consistent across platforms.

You can also adjust the value based on your specific scenario. The value can range from 0 to 1, including decimal values such as 0.1, 0.2, etc.

## Notes

- The SideDrawer control has different implementations for iOS, Android, and WinUI, which is why the behavior differs across platforms.
- Adjusting the `DrawerTransitionFadeOpacity` property allows you to achieve consistency in the SideDrawer content across different platforms.
- Make sure to set the appropriate value for the desired platform, taking into account the range from 0 to 1.

## See Also

- [SideDrawer Documentation](https://docs.telerik.com/devtools/xamarin/controls/sidedrawer/sidedrawer-overview)
