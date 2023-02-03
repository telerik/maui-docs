---
title: Migrating from Xamarin
page_title: Migrating the ListView from Xamarin.Forms to .NET MAUI
description: "Learn how to migrate the Telerik UI for Xamarin ListView to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages. "
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
slug: migrate-to-net-maui
position: 2
---

# Migrating the ListView from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI ListView preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

...

The following example shows how to disable the bounce effect for the .NET MAUI ListView on iOS by using the custom renderer of the Xamarin ListView.

**1.** Port the custom renderer to a handler.

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

**2.** To access the native view and apply the customizations, you have to use the `HandlerChanged` event in .NET MAUI and first subscribe to the `HandlerChanged` event by using your `RadListView` instance:

```C#
this.listView.HandlerChanged += ListView_HandlerChanged;
```

**3.** Inside the `ListView_HandlerChanged` event handler, use preprocessor directives for iOS, access the native ListView control, and apply the required settings:

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

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
