---
title: Commands
page_title: .NET MAUI CollectionView Documentation - Commands
description: Review the Telerik UI for .NET MAUI CollectionView Commands for operations like item tap and item holding.
position: 20
slug: collectionview-commands
tags: commands, collectionview, mvvm, maui, dotnet maui
---

# .NET MAUI CollectionView Commands

The .NET MAUI CollectionView provides various commands that are listed in the following table.

| Commands | Definition |
| -------- | ---------- |
| `ItemTappedCommand`(`ICommand`) | Specifies a command to execute when an item is tapped. The command accepts a single parameter with the item being tapped. |
| `GroupTappedCommand`(`ICommand`) | Specifies a command to execute when a group item is tapped. The command accepts a single parameter with the group item being tapped. |

>tip Commands action correspond to the events exposed by the CollectionView. For more details, see the [Events]({%slug collectionview-events%}) topic.


### Example with GroupItemTapped Command

**1.** Create a sample model:

<snippet id='collectionview-grouptapcommand-model' />

**2.** Create a `ViewModel` with a command that will be bind to the `RadCollectionView.GroupItemTappedCommand`:

<snippet id='collectionview-grouptapcommand-viewmodel' />

**3.** Define the CollectionView control with a sample `ItemTemplate`:

<snippet id='commectionview-grouptapcommand' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```	

> For a runnable example demonstrating the CollectionView Commands, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CollectionView > Commands** category.

## See Also

- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Selection]({%slug collectionview-selection%})
- [Events]({%slug collectionview-events%})