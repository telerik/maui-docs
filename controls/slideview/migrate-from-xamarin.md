---
title: Migrating from Xamarin
page_title: Migrating the SlideView from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin SlideView to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
slug: migrate-xamarin-slideview-to-maui
position: 20
---

# Migrating the SlideView from Xamarin to .NET MAUI  

The Telerik UI for .NET MAUI SlideView and the Xamarin SlideView have some differences in the API and the available configuration options. When migrating the SlideView component from Xamarin to .NET MAUI, consider the differences listed in this article.

## Namespaces Differences

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin SlideView | `RadSlideView` | `xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input"` | `using Telerik.XamarinForms.Input;` | 
| .NET MAUI SlideView | `RadSlideView` | `xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | `using Telerik.Maui.Controls;` |


## API Differences

| Xamarin SlideView | .NET MAUI SlideView |
| ------------- | --------------- |
| `IsSwipingEnabled` | `SlideViewInteractionMode` |
| [Indicator customization options in Xamarin](https://docs.telerik.com/devtools/xamarin/controls/slideview/customize-the-control#customizing-the-indicators)   | [Indicator configuration options in .NET MAUI]({%slug indicators-styling%}) |
| NA | `OverScrollMode` |
| `PageSpacingProperty` | `Spacing` |
| `IsAnimated` | NA |
| [Controlling the alignment of the content](https://docs.telerik.com/devtools/xamarin/controls/slideview/customize-the-control#customizing-the-content-alignment) | NA |
| `IsInfiniteScrollingEnabled` | `HasLooping` |
| [Customization properties for the slide buttons](https://docs.telerik.com/devtools/xamarin/controls/slideview/customize-the-control#customizing-the-slide-buttons) | [Styling properties for the Navigation Buttons]({%slug slideview-navigation-buttons-styling%}) |
| `ItemTemplateSelector` | NA |
