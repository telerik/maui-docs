---
title: Removing ManualLoadOnDemandTemplate in CollectionView for .NET MAUI When No More Items Are Available
description: Learn how to remove or hide the ManualLoadOnDemandTemplate in CollectionView for .NET MAUI when there are no more items to load.
type: how-to
page_title: Hiding CollectionView ManualLoadOnDemandTemplate When No More Items to Load in .NET MAUI
meta_title: Hiding CollectionView ManualLoadOnDemandTemplate When No More Items to Load in .NET MAUI
slug: removing-manualloadondemandtemplate-collectionview-dotnet-maui
tags: collectionview, .net maui, manualloadondemandtemplate, isloadondemandenabled
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want the `ManualLoadOnDemandTemplate` of the [CollectionView]({%slug collectionview-overview%}) for .NET MAUI to disappear when there are no more items to load. The template currently remains visible even after all data has been loaded.

This knowledge base article also answers the following questions:
- How can I disable the `ManualLoadOnDemandTemplate` in CollectionView for .NET MAUI?
- What property controls the visibility of the `ManualLoadOnDemandTemplate` in CollectionView?
- How do I stop the load-on-demand feature in CollectionView for .NET MAUI?

## Solution

To remove or hide the `ManualLoadOnDemandTemplate` when no more items need to be loaded, set the `IsLoadOnDemandEnabled` property of the CollectionView to `false`. This property controls whether the load-on-demand functionality is active. Disabling it hides the `ManualLoadOnDemandTemplate`.

Here is an example:

**1.** Define the `ViewModel`

```csharp
public partial class LoadOnDemandCollectionViewModel : NotifyPropertyChangedBase
{
    private bool isEnabled = true;

    public LoadOnDemandCollectionViewModel()
    {
        this.Items = new LoadOnDemandCollection<Person>(this.LoadMoreItems);

        for (int i = 0; i < 20; i++)
        {
            this.Items.Add(new Person { Name = "Person " + i, Age = i + 10 });
        }
    }

    public LoadOnDemandCollection<Person> Items { get; set; }

    public bool IsEnabled
    {
        get => this.isEnabled;
        set => this.UpdateValue(ref this.isEnabled, value);
    }

    private IEnumerable LoadMoreItems(CancellationToken cancellationToken)
    {
        List<Person> newItems = new List<Person>();
        int count = this.Items.Count;

        // Simulate a limit for loading more items
        if (count >= 30)
        {
            this.IsEnabled = false; // Disable load-on-demand
            return null; // No more items to load
        }

        for (int i = count; i < count + 10; i++)
        {
            newItems.Add(new Person { Name = "Person " + i, Age = i + 10 });
        }

        return newItems;
    }
}
```

**2.** Bind the `IsLoadOnDemandEnabled` property of the `RadCollectionView` to a property in your ViewModel, such as `IsEnabled`:

```xml
<telerik:RadCollectionView x:Name="listView"
                           ItemsSource="{Binding Items}"
                           DisplayMemberPath="Name"
                           LoadOnDemandMode="Manual"
                           IsLoadOnDemandEnabled="{Binding IsEnabled, Mode=TwoWay}" />
```

## See Also

- [CollectionView Overview]({%slug collectionview-overview%})
- [Load on Demand in .NET MAUI CollectionView]({%slug collectionview-load-on-demand%})
