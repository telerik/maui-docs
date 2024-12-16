---
title: RadCollectionView Drag and Swipe Do Not Work Inside ScrollView in .NET MAUI
description: Learn how to address the issues where RadCollectionView drag and swipe do not work inside a ScrollView in .NET MAUI applications.
type: troubleshooting
page_title: Fixing RadCollectionView Scroll Issues Inside ScrollView in .NET MAUI
slug: collectionview-not-scrolling-inside-scrollview
tags: collectionview, .net maui, scrollview, scrolling, ui virtualization
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 8.0.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

When using RadCollectionView inside a ScrollView in a .NET MAUI application, the RadCollectionView does not scroll during item drag or swipe actions. 

## Cause

Nesting scrollable controls, such as RadCollectionView, within a ScrollView is discouraged as it breaks UI virtualization and leads to various issues. This is documented in the [Microsoft documentation](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/scrollview?view=net-maui-9.0), which advises against nesting ScrollView objects with other controls that provide their own scrolling functionality.

## Solution

To resolve the scrolling issue with RadCollectionView when it's placed inside a ScrollView, consider the following approaches:

### Approach 1: Remove the ScrollView

Eliminate the ScrollView from your layout. This allows `RadCollectionView` to manage its own scrolling behavior effectively without interference.

### Approach 2: Set a Definitive Height

Assign a definitive height to `RadCollectionView` or any control that has internal scrolling. This adjustment helps in defining the control's scrollable area explicitly, thereby preventing conflicts with the ScrollView.

By applying one of these solutions, `RadCollectionView` will scroll as expected when it is used within a ScrollView in a .NET MAUI application.

## See Also

- [ScrollView documentation by Microsoft](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/scrollview?view=net-maui-9.0)
- [CollectionView Overview](https://docs.telerik.com/devtools/maui/controls/collectionview/overview)

