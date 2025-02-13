---
title: Synchronizing Scrolling Between Two DataGrid Controls in MAUI
description: Learn how to synchronize horizontal and vertical scrolling between two DataGrid controls in a MAUI application.
type: how-to
page_title: How to Sync Scrolling for Two DataGrids in MAUI
slug: sync-scrolling-datagrid-maui
tags: datagrid, maui, scroll, synchronize, radscrollview
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In a scenario where two DataGrid controls are placed side by side, the requirement is to synchronize their scrolling. When one DataGrid is scrolled either horizontally or vertically, the second DataGrid should scroll in sync with the first one.

This knowledge base article also answers the following questions:
- How can I link the scroll position of two DataGrids in MAUI?
- Is it possible to synchronize horizontal scrolling between two DataGrid controls?
- Can vertical scrolling be synced between DataGrids in a MAUI application?

## Solution

To achieve synchronized scrolling between two DataGrid controls, utilize the `RadScrollView` within each DataGrid. By handling the `Scrolled` event of the first DataGrid's `RadScrollView`, you can programmatically scroll the second DataGrid to match the scroll position of the first DataGrid. Follow the steps below to implement this solution:

1. Identify the `RadScrollView` within each DataGrid. This can be done by iterating through the children of the DataGrid and checking for the `RadScrollView` type.

2. Attach a handler to the `Scrolled` event of the first DataGrid's `RadScrollView`.

3. In the event handler, get the scroll position (`ScrollX` and `ScrollY`) from the event args.

4. Scroll the second DataGrid's `RadScrollView` to the same position using the `ScrollToAsync` method.

Here is a code snippet demonstrating these steps:

```csharp
public partial class MainPage : ContentPage
{
	public MainPage()
	{
		InitializeComponent();

		var data = new ObservableCollection<Data>();
		for (int i = 0; i < 30; i++)
		{
			data.Add(new Data { Address = "Address" + i, Capital = "Capital" + i, Country = "Country " + i, MyData = "My Data" + i, Name = "Name " + i });
		}
		this.grid1.ItemsSource = data;


		var data2 = new ObservableCollection<Data>();
		for (int i = 0; i < 30; i++)
		{
			data2.Add(new Data { Address = "Address" + i, Capital = "Capital" + i, Country = "Country " + i, MyData = "My Data" + i, Name = "Name " + i });
		}
		this.grid2.ItemsSource = data2;

		RadScrollView sv1 = FindRadScrollView(this.grid1);
		if (sv1 != null)
		{
			sv1.Scrolled += Sv_Scrolled;
		}
	}

	private void Sv_Scrolled(object? sender, ScrolledEventArgs e)
	{
		var x = e.ScrollX;
		var y = e.ScrollY;

		RadScrollView sv2 = FindRadScrollView(this.grid2);
		sv2?.ScrollToAsync(x, y, true);
	}

	private RadScrollView? FindRadScrollView(RadDataGrid grid)
	{
		foreach (var child in grid)
		{
			if (child is RadScrollView sv)
			{
				return sv;
			}
		}
		return null;
	}
}
```

In this solution, `FindRadScrollView` is a helper method that iterates through the children of a DataGrid to find the `RadScrollView`. Once the `RadScrollView` is found and its `Scrolled` event is hooked, any scroll action on the first DataGrid triggers the `Sv_Scrolled` event handler, which then scrolls the second DataGrid accordingly.

## See Also

- [DataGrid Overview]({%slug datagrid-overview%})
