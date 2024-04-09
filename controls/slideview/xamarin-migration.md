---
title: Migrating from Xamarin
page_title: Migrating the SlideView from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin SlideView to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
previous_url: /controls/slideview/migrate-from-xamarin
slug: migrate-xamarin-slideview-to-maui
position: 20
---

# Migrating the SlideView from Xamarin to .NET MAUI  

The Telerik UI for .NET MAUI SlideView control has been designed and built from the ground up as a new control with a new API and significant improvements over its Xamarin counterpart.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms SlideView and .NET MAUI SlideView.

## Namespaces Differences

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin SlideView | `RadSlideView` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; | 
| .NET MAUI SlideView | `RadSlideView` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |


## API Differences

| Xamarin SlideView | .NET MAUI SlideView |
| ------------- | --------------- |
| `IsSwipingEnabled` | `InteractionMode` |
| [Indicator customization options in Xamarin](https://docs.telerik.com/devtools/xamarin/controls/slideview/customize-the-control#customizing-the-indicators)   | [Indicator configuration options in .NET MAUI]({%slug indicators-styling%}) |
| `PageSpacing` | `Spacing` |
| `IsAnimated` | Set `AnimationDuration=0` |
| [Controlling the alignment of the content](https://docs.telerik.com/devtools/xamarin/controls/slideview/customize-the-control#customizing-the-content-alignment) | N/A |
| `IsInfiniteScrollingEnabled` | `HasLooping` |
| [Customization properties for the slide buttons](https://docs.telerik.com/devtools/xamarin/controls/slideview/customize-the-control#customizing-the-slide-buttons) | [Styling properties for the Navigation Buttons]({%slug slideview-navigation-buttons-styling%}) |
| `ItemTemplateSelector` | `ItemTemplate` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
* [.NET MAUI SlideView Product Page](https://www.telerik.com/maui-ui/slideview)
* [Telerik .NET MAUI Blogs](https://www.telerik.com/forums/maui?tagId=2058)

