---
title: Migrating from Xamarin
page_title: Migrating the SlideView from Xamarin.Forms to .NET MAUI
description: "Learn how to migrate the Telerik UI for Xamarin SlideView to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages."
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
slug: migrate-xamarin-slideview-to-maui
position: 3
---

# Migrating the SlideView from Xamarin to .NET MAUI  

The Telerik UI for .NET MAUI SlideView has some changes to the API and configuration options. They are listed in this article.

## Migrate Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin SlideView | `RadSlideView` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; | 
| .NET MAUI SlideView | `RadSlideView` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |


## API Changes

| Xamarin SlideView | .NET MAUI SlideView |
| ------------- | --------------- |
| `IsSwipingEnabled` | `SlideViewInteractionMode` |
| [Indicator Customization Options](https://docs.telerik.com/devtools/xamarin/controls/slideview/customize-the-control#customizing-the-indicators)   | `Indicator Styling`- Indicators are separated form the SlideView ({%slug indicators-styling%})  |
| - | `OverScrollMode` |
| `PageSpacingProperty` | `Spacing` |
| `IsAnimated` | - |
| [Customizing the content alignment](https://docs.telerik.com/devtools/xamarin/controls/slideview/customize-the-control#customizing-the-content-alignment) | - |
| `IsInfiniteScrollingEnabled` | `HasLooping` |
| [Customizing the slide buttons](https://docs.telerik.com/devtools/xamarin/controls/slideview/customize-the-control#customizing-the-slide-buttons) | SlideView exposes a styling properties about the `Navigation Buttons` ({%slug slideview-styling%}) |
| `ItemTemplateSelector` | - |