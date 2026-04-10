---
title: Preventing Automatic Sorting of Groups in CollectionView
description: Learn how to prevent automatic group sorting in RadCollectionView for UI for .NET MAUI by implementing a custom solution.
type: how-to
page_title: Avoid Automatic Group Sorting in CollectionView
meta_title: Avoid Automatic Group Sorting in CollectionView for .NET MAUI
slug: prevent-automatic-sorting-groups-collectionview
tags: radcollectionview,.net maui,group sorting,custom group order
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 13.0.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

CollectionView in UI for .NET MAUI automatically sorts groups based on the `SortOrder` property of the group descriptors. By default, groups are arranged in ascending or descending order alphabetically. There is no built-in way to preserve the order of groups as they appear in the data source.

## Solution

To maintain the original order of groups as they appear in the data source, implement a custom grouping logic by introducing an additional property that represents the group index. The steps below demonstrate how to achieve this:

1. Add a `GroupId` property to your data model to represent the custom group order along with a descriptive property for grouping (e.g., `Country`).

```csharp
// Data Model with GroupId for custom group order
public class DataModel
{
    public string Continent { get; set; }
    public string Country { get; set; }
    public string City { get; set; }
    public int Id { get; set; }
    public int GroupId { get; set; }
}

// ObservableCollection with data and GroupId for order
this.Locations = new ObservableCollection<DataModel>
{
    new DataModel { Continent = "Europe", Country = "Austria", City = "Graz", Id = 1, GroupId = 3 },
    new DataModel { Continent = "Europe", Country = "Belgium", City = "Antwerp", Id = 5, GroupId = 1 },
    new DataModel { Continent = "Europe", Country = "Denmark", City = "Copenhagen", Id = 8, GroupId = 2 },
    // Add more data as needed
};
```

2. Use the `GroupId` property for grouping in the `GroupDescriptors` of RadCollectionView.
3. Utilize a `GroupHeaderTemplate` to display the correct group header text.

```xml
<telerik:RadCollectionView ItemsSource="{Binding Locations}"
                           DisplayMemberPath="City">
    <telerik:RadCollectionView.BindingContext>
        <local:ViewModel />
    </telerik:RadCollectionView.BindingContext>
    <telerik:RadCollectionView.GroupHeaderTemplate>
        <DataTemplate>
            <Label TextColor="Black" VerticalTextAlignment="Center">
                <Label.FormattedText>
                    <FormattedString>
                        <Span Text="Country: " />
                        <Span Text="{Binding Items[0].Country}" TextColor="#00796B" FontAttributes="Bold" />
                    </FormattedString>
                </Label.FormattedText>
            </Label>
        </DataTemplate>
    </telerik:RadCollectionView.GroupHeaderTemplate>
    <telerik:RadCollectionView.GroupDescriptors>
        <telerik:PropertyGroupDescriptor PropertyName="GroupId" />
    </telerik:RadCollectionView.GroupDescriptors>
</telerik:RadCollectionView>
```

This approach ensures the group order is determined by the `GroupId` property rather than the default sorting logic.

## See Also

- [CollectionView Documentation](https://www.telerik.com/maui-ui/documentation/controls/collectionview/overview)  
- [Grouping in RadCollectionView](https://www.telerik.com/maui-ui/documentation/controls/collectionview/grouping/overview) 
