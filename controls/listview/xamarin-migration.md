---
title: Migrating from Xamarin
page_title: Migrating the ListView from Xamarin.Forms to .NET MAUI
description: "Learn how The steps include converting the projects from .NET Framework to .NET SDK style, updating namespaces and any incompatible NuGet packages and a few more. "
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
slug: migrate-to-net-maui
position: 40
---

# Migrating the ListView from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI ListView preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

...

The following example shows how to disable the bounce effect for the .NET MAUI ListView on iOS by using the custom renderer of the Xamarin ListView.

```C#
using Xamarin.Forms;
using Xamarin.Forms.Platform.iOS;
using MyXamarinApp.iOS;
using Telerik.XamarinForms.DataControls;

[assembly: ExportRenderer(typeof(RadListView), typeof(CustomListViewRenderer))]
namespace MyXamarinApp.iOS
{
    public class CustomListViewRenderer : Telerik.XamarinForms.DataControlsRenderer.iOS.ListViewRenderer
    {
        protected override void OnElementChanged(ElementChangedEventArgs<RadListView> e)
        {
            base.OnElementChanged(e);

            var nativeListView = this.Control as Telerik.XamarinForms.DataControlsRenderer.iOS.TKExtendedListView;
            if (nativeListView != null)
            {
                nativeListView.Layout.CollectionView.Bounces = false;
            }
        }
    }
}
```

In .NET MAUI you would need to use the `HandlerChanged` event to access the native view and apply any customizations. So, first subscribe to `HandlerChanged` using your `RadListView` instance:

```C#
this.listView.HandlerChanged += ListView_HandlerChanged;
```

Then, inside the "ListView_HandlerChanged" event handler use preprocessor directives for iOS, access the native ListView control and apply the required settings:

```C#
private void ListView_HandlerChanged(object sender, EventArgs e)
{
	var handler = ((RadListView)sender).Handler;
	if (handler != null)
	{
#if __IOS__
		var nativeView = handler.PlatformView as Telerik.Maui.Controls.Compatibility.DataControlsRenderer.iOS.TKExtendedListView;
		nativeView.Layout.CollectionView.Bounces = false;
#endif
    }
}
```

## See Also

- [Telerik UI for .NET Sample Applications]({% slug sampleapps-overview %})
