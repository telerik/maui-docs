---
title: Enabling Events in EmptyContentTemplate for CollectionView in .NET MAUI
description: Learn how to enable GestureRecognizer and Button Click events in the EmptyContentTemplate of the CollectionView for .NET MAUI when they are not executing.
type: how-to
page_title: Resolving Event Execution Issues in EmptyContentTemplate of CollectionView in .NET MAUI
slug: collectionview-emptycontenttemplate-events-net-maui
tags: collectionview, .net maui, emptycontenttemplate, gesturerecognizer, button-click, inputtransparent
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I am using the `EmptyContentTemplate` in the [CollectionView for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/collectionview/overview) to display custom content when the `ItemsSource` is empty or null. Inside the template, `GestureRecognizer` and Button `Click` events are defined, but they do not execute as expected. This behavior occurs because the control's default implementation sets the template's transparency to `true`, which makes it ignore input events.

This knowledge base article also answers the following questions:
- How to make `GestureRecognizer` events work in `EmptyContentTemplate`?
- Why are Button `Click` events not firing in CollectionView `EmptyContentTemplate`?
- How to disable transparency for `EmptyContentTemplate` in .NET MAUI CollectionView?

## Solution

To enable `GestureRecognizer` or Button `Click` events in the `EmptyContentTemplate`, you need to disable the transparency of the template. Use the following approach:

**1.** Set the `EmptyContentDisplayMode` property to `ItemsSourceNullOrEmpty`.

```xaml
<telerik:RadCollectionView x:Name="collection" 
                           EmptyContentDisplayMode="ItemsSourceNullOrEmpty">
    <telerik:RadCollectionView.EmptyContentTemplate>
        <DataTemplate>
            <Grid RowDefinitions="Auto,Auto" Padding="0,40,0,0">
                <Grid.GestureRecognizers>
                    <TapGestureRecognizer NumberOfTapsRequired="1" Tapped="OnEmptyContentTapped"/>
                </Grid.GestureRecognizers>
                <Label Grid.Row="0" Text="Nothing Found to Display"
                       HorizontalTextAlignment="Center"
                       TextColor="Black"/>
                <Button Grid.Row="1" Text="Add New" 
                        Margin="0,10,0,0"
                        HorizontalOptions="Center"
                        Clicked="OnAddNewButtonClicked"/>
            </Grid>                        
        </DataTemplate>                            
    </telerik:RadCollectionView.EmptyContentTemplate>
</telerik:RadCollectionView>
```
**2.** Access the last child of the CollectionView and set its `InputTransparent` property to `false`.

```csharp
var emptyContent = (View)this.collection.Last();
emptyContent.InputTransparent = false;

private async void OnAddNewButtonClicked(object sender, EventArgs e)
{
    await DisplayAlert("Clicked", "Add New Clicked", "OK");
}             

private async void OnEmptyContentTapped(object sender, TappedEventArgs e)
{
    await DisplayAlert("Tapped", "Empty Content Tapped", "OK");
}
```

Setting `InputTransparent` to `false` ensures that the `EmptyContentTemplate` can respond to input events like `GestureRecognizer` taps and Button clicks.

## See Also

- [CollectionView Overview for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/collectionview/overview)
- [EmptyContentTemplate in CollectionView for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/collectionview/empty-template)
- [GestureRecognizer in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/gestures/tap?view=net-maui-9.0)
