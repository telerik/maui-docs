---
title: SideDrawer MainContent Size Incorrect After Orientation Change
description: Learn how to resolve the SideDrawer MainContent size issue after changing device orientation in UI for .NET MAUI.
type: troubleshooting
page_title: Resolving SideDrawer MainContent Height Issue After Device Rotation
meta_title: Fixing SideDrawer MainContent Size Calculation on Orientation Change
slug: sidedrawer-maincontent-size-issue-after-orientation-change
tags: sidedrawer, ui-for-dotnet-maui, orientation, maincontent, resize
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 12.0.0 | Telerik UI for .NET MAUI SideDrawer | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

When using [SideDrawer](https://www.telerik.com/maui-ui/documentation/controls/sidedrawer/overview) with a bottom margin, the `MainContent` size calculation becomes incorrect after changing device orientation. This occurs when the following steps are performed:

1. Open RadSideDrawer in landscape orientation.
2. Close RadSideDrawer.
3. Change device orientation to portrait.
4. Open RadSideDrawer again.

**Actual result:** In portrait mode, the `MainContent` retains the height from landscape mode, making the content appear shorter than expected.

**Expected result:** `MainContent` should automatically adjust its size according to the new orientation.

## Cause

This behavior is caused by the SideDrawer's views not being invalidated or updated after the orientation change.

## Solution

To resolve the issue, use one of the following approaches:

### Approach 1: Override `OnSizeAllocated`

Override the `OnSizeAllocated` method to close the drawer during orientation changes and call the `UpdateDrawer()` method.

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.drawer.HandlerChanged += drawer_HandlerChanged;
    }

    protected override void OnSizeAllocated(double width, double height)
    {
        base.OnSizeAllocated(width, height);
        this.UpdateDrawer();

        if (this.drawer != null && this.drawer.IsOpen == true)
        {
            this.drawer.IsOpen = false;
        }
    }

    private void OpenDrawer_Clicked(object sender, EventArgs e)
    {
        this.drawer.IsOpen = true;
    }

    private void drawer_HandlerChanged(object sender, EventArgs e)
    {
        this.UpdateDrawer();
    }

    private void UpdateDrawer()
    {
        var platformView = this.drawer.Handler.PlatformView;

#if IOS || MACCATALYST
        var platformSideDrawer = (TelerikUI.TKSideDrawerView)platformView;
        var drawer = platformSideDrawer.SideDrawers[0];
        drawer.Style.HeaderHeight = 0;
        drawer.Style.FooterHeight = 0;
#endif
    }
}
```

### Approach 2: Invalidate SideDrawer Views

Invalidate the SideDrawer's views during `OnSizeAllocated` and when opening the SideDrawer.

```csharp
protected override void OnSizeAllocated(double width, double height)
{
    base.OnSizeAllocated(width, height);

    (this.drawer.DrawerContent as IView)?.InvalidateMeasure();
    (this.drawer.MainContent as IView)?.InvalidateMeasure();

    this.Dispatcher.Dispatch(() =>
    {
        var platformView = this.drawer?.Handler?.PlatformView as TelerikUI.TKSideDrawerView;
        if (platformView != null)
        {
            var hostView = platformView.MainView.Superview;
            if (hostView != null)
            {
                var layer = hostView.Layer?.Sublayers?.LastOrDefault() as CALayer;
                if (layer != null)
                {
                    layer.Frame = new CoreGraphics.CGRect(0, 0, hostView.Frame.Width, hostView.Frame.Height);
                }
            }
        }
    });
}

private void OpenDrawer_Clicked(object sender, EventArgs e)
{
    this.drawer.IsOpen = true;
    (this.drawer.DrawerContent as IView)?.InvalidateMeasure();
}
```

## See Also

- [SideDrawer Documentation](https://www.telerik.com/maui-ui/documentation/controls/sidedrawer/overview)
- [Known Issue - SideDrawer: [iOS] Content views don't resize on rotation](https://feedback.telerik.com/maui/1655241-sidedrawer-ios-content-views-don-t-resize-on-rotation)
