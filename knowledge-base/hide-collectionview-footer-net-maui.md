---
title: Hiding the CollectionView Footer in .NET MAUI
description: Learn how to hide the footer of the RadCollectionView in a .NET MAUI application.
type: how-to
page_title: How to Hide the Footer in Telerik CollectionView for .NET MAUI
slug: hide-collectionview-footer-net-maui
tags: collectionview, footer, hide, .net maui, telerik
res_type: kb
---

## Environment

| Product | Version |
| --- | --- |
| CollectionView for .NET MAUI | 7.1.0 |

## Description

When working with the [CollectionView]({%slug collectionview-overview%}) in .NET MAUI, there might be scenarios where you need to hide the footer. This could be due to dynamic content changes or simply because the footer is not needed in certain contexts.

This KB article also answers the following questions:
- How can I remove the footer from the CollectionView in .NET MAUI?
- What is the method to hide the footer in Telerik CollectionView?
- Can I conditionally display the footer in a CollectionView?

## Solution

To hide the footer in the `RadCollectionView`, you can utilize a `ContentView` and set the `IsVisible` property to `False`. This method allows for dynamic changes if needed, as the visibility can be toggled based on your application's logic.

Here is an example of how to implement this in XAML:

```XAML
<telerik:RadCollectionView.FooterTemplate>
    <DataTemplate>
        <ContentView IsVisible="False">
            <telerik:RadBorder BorderColor="PaleVioletRed" IsVisible="False"
                        BorderThickness="0, 1"
                        BackgroundColor="#F3F3F3">
                <Grid ColumnDefinitions="Auto, *">
                    <Label Text="Total cities: "
                    Margin="10"
                    TextColor="PaleVioletRed"/>
                    <Label Text="{Binding ItemsSource.Count, Source={x:Reference collectionView}}"
                    Grid.Column="1"
                    Margin="10"
                    TextColor="PaleVioletRed"/>
                </Grid>
            </telerik:RadBorder>
        </ContentView>
    </DataTemplate>
</telerik:RadCollectionView.FooterTemplate>
```

In this example, the `FooterTemplate` is wrapped in a `ContentView` with the `IsVisible` property set to `False`. This effectively hides the footer from view while keeping the code needed for the footer in place, should you wish to make it visible again at a later point.
