---
title: Removing Selection Indicator from CollectionView on Windows
description: Learn how to remove the selection indicator from a CollectionView in a .NET MAUI application running on Windows.
type: how-to
page_title: How to Remove the Selection Indicator from RadCollectionView in Windows
slug: remove-selection-indicator-collectionview-windows
tags: collectionview, .net maui, windows, radcollectionviewitemview, selection, indicator, control template, style
res_type: kb
---

## Environment

| Product | Version | Author |
| --- | --- | --- | 
| CollectionView for .NET MAUI | 7.1.0 | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When using a `RadCollectionView` in a .NET MAUI application on Windows, the default behavior includes a selection indicator on items that are selected. This article demonstrates how to remove the selection indicator from CollectionView by updating the control template.

This KB article also answers the following questions:
- How can I customize the appearance of selected items in RadCollectionView on Windows?
- What steps are needed to modify the control template of CollectionView?
- How do I apply a custom style to CollectionView in .NET MAUI?

## Solution

To remove the selection indicator from `RadCollectionView` on Windows, follow these steps:

1. Define a new `ControlTemplate` that omits the selection indicator and other undesired visual elements.
2. Create a `Style` for `RadCollectionViewItemView` that applies this `ControlTemplate`.
3. Apply the `Style` to `RadCollectionViewItemView` either implicitly within the `ResourceDictionary` or explicitly through the `ItemViewStyle` property.

### Example of Implicit Style

Add the following XAML to your .NET MAUI page to apply the style implicitly:

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <ControlTemplate x:Key="RadCollectionViewItem_ControlTemplate_WinUI">
            <ContentPresenter />
        </ControlTemplate>

        <Style TargetType="telerik:RadCollectionViewItemView">
            <Setter Property="BorderColor" Value="#80CBC4" />
            <Setter Property="ControlTemplate" Value="{StaticResource RadCollectionViewItem_ControlTemplate_WinUI}"/>
            <Setter Property="BorderThickness" Value="0, 0, 0, 1" />
            <Setter Property="CornerRadius" Value="0" />
            <Setter Property="VisualStateManager.VisualStateGroups">
                <VisualStateGroupList>
                    <VisualStateGroup Name="CommonStates">
                        <VisualState Name="Normal" />
                        <VisualState Name="MouseOver">
                            <VisualState.Setters>
                                <Setter Property="BackgroundColor" Value="#D6EEEC" />
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState Name="Selected">
                            <VisualState.Setters>
                                <Setter Property="BackgroundColor" Value="#C4E6E3" />
                            </VisualState.Setters>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateGroupList>
            </Setter>
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
<telerik:RadCollectionView ItemsSource="{Binding Locations}"
                           SelectionMode="Multiple"
                           SelectedItems="{Binding SelectedLocations}"
                           DisplayMemberPath="City">
    <telerik:RadCollectionView.BindingContext>
        <local:ViewModel />
    </telerik:RadCollectionView.BindingContext>
</telerik:RadCollectionView>
```

### Using Explicit Style

To use an explicit style, set the above-defined style to the `RadCollectionView.ItemViewStyle` property. Refer to the [official documentation]({%slug collectionview-item-styling%}) for more details on using explicit styles.

## See Also

- [RadCollectionView Styling Documentation]({%slug collectionview-item-styling%})
- [RadCollectionView Overview]({%slug collectionview-overview%})
