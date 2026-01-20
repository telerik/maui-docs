---
title: Popup Shrinks When Soft Keyboard Opens on mobile
description: Address the issue of Popup shrinking when the soft keyboard opens on mobile and provide solutions.
type: troubleshooting
page_title: RadPopup Behavior with Soft Keyboard on Android and iOS
meta_title: RadPopup Behavior with Soft Keyboard on Android and iOS
slug: radpopup-shrinks-soft-keyboard-android
tags: popup, ui-for-net-maui, android, keyboard, displacement, ios
res_type: kb
---

## Environment

| Product | Author | 
| --- | ---- | 
| Telerik UI for .NET MAUI Popup | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

When the soft keyboard opens on Android or iOS while a [RadPopup](https://www.telerik.com/maui-ui/documentation/controls/popup/overview) containing an input is displayed, the popup shrinks to fit the remaining visible area above the keyboard instead of maintaining its height. This prevents the popup from using scrolling to reach the input field if needed.

## Cause

When the soft keyboard opens, the available visible space on the screen decreases. The `RadPopup` adjusts to fit within this space, which can cause displacement or resizing. This behavior is intentional to prioritize displaying popup content within the visible area. However, if the popup content exceeds the screen size, parts of it may go out of view. 

## Solution

To prevent the `RadPopup` from shrinking when the keyboard opens, apply one of the following solutions:

* [Avoid Large Popup Sizes](#avoid-large-popup-sizes)
* [Use Overlay Instead of RadPopup](#use-overlay-instead-of-radpopup)

### Avoid Large Popup Sizes

Avoid setting the popup content size larger than the visible area. This ensures the popup fits within the screen even when the keyboard opens.

### Use Overlay Instead of RadPopup

Replace the `RadPopup` with an overlay that remains unaffected by keyboard displacement. Create a grid and toggle the visibility of an overlay for similar functionality:

```xml
<Grid>
  <Grid x:Name="originalContent" />
  <Grid x:Name="overlay" IsVisible="False" BackgroundColor="LightGray">
    <!-- Overlay Content -->
  </Grid>
</Grid>
```

Set the `IsVisible` property of the overlay to `True` to display it.

## See Also

- [Popup Documentation](https://www.telerik.com/maui-ui/documentation/controls/popup/overview)
