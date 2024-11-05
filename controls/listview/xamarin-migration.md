---
title: Migrating from Xamarin
page_title: Migrating the ListView from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin ListView to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
slug: migrate-xamarin-listview-to-maui
position: 20
---

>caution ListView control is now obsolete and will be removed in future. [CollectionView]({%slug collectionview-overview%}) is a complete rewrite of the ListView from the ground up. The CollectionView offers improved performance, enhanced features, and a modernized approach to managing lists of data. The CollectionView incorporates all key features of the ListView. You can read about the differences between both components and how to migrate to the new CollectionView in the following article: [Migrating the Telerik .NET MAUI ListView to CollectionView]({%slug listview-migration%}).

# Migrating the ListView from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI ListView preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

## Step 1: Convert the ListView to .NET MAUI

For the purposes of this guide, take the following scenario:

**1.** You have the following `RadListView` definition in a Xamarin application:

```XAML
<telerikDataControls:RadListView x:Name="listView" ItemsSource="{Binding Source}">
    <telerikDataControls:RadListView.ItemTemplate>
        <DataTemplate>
            <telerikListView:ListViewTemplateCell>
                <telerikListView:ListViewTemplateCell.View>
                    <Grid>
                        <Label Margin="10" Text="{Binding Name}" />
                    </Grid>
                </telerikListView:ListViewTemplateCell.View>
            </telerikListView:ListViewTemplateCell>
        </DataTemplate>
    </telerikDataControls:RadListView.ItemTemplate>
</telerikDataControls:RadListView>
```

In this Xamarin project, the namespaces are defined as follows:

```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.XamarinForms.DataControls"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.XamarinForms.DataControls"         
```

**2.** In the .NET MAUI project, replace the namespaces in the following way:

```XAML
<telerik:RadListView x:Name="listView" ItemsSource="{Binding Source}">
    <telerik:RadListView.ItemTemplate>
        <DataTemplate>
            <telerik:ListViewTemplateCell>
                <telerik:ListViewTemplateCell.View>
                    <Grid>
                        <Label Margin="10" Text="{Binding Name}" />
                    </Grid>
                </telerik:ListViewTemplateCell.View>
            </telerik:ListViewTemplateCell>
        </DataTemplate>
    </telerik:RadListView.ItemTemplate>
</telerik:RadListView>
```

**3.** Also, add the common `telerik` namespace to the .NET MAUI project:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Step 2: Port the ListView Custom Renderers to Handlers  

In this step, you will disable the bounce effect for the .NET MAUI ListView on iOS by using the custom renderer of the Xamarin ListView.

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

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI ListView Product Page](https://www.telerik.com/maui-ui/listview)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
