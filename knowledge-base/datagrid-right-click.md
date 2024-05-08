---
title: Cell Info on Right Click in DataGrid
description: Get the cell info on right click in the RadDataGrid for .NET MAUI.
type: how-to
page_title: Right click on DataGrid
slug: datagrid-right-click
position: 
tags: 
ticketid: 1608289
res_type: kb
---

## Environment
| Version | Product | Author | 
| --- | --- | ---- | 
| 5.1.0 | Telerik UI for .NET MAUI Chart | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

This how-to article describes how to get the cell info on a right click in the Telerik UI for .NET MAUI DataGrid control.

## Solution

**1.** Add DataGrid to the Page:

```XAML
<Grid>
	<telerik:RadDataGrid x:Name="dataGrid" />
</Grid>
```

**2.** Add Sample data to the `RadDataGrid.ItemsSource`:

```C#
this.dataGrid.ItemsSource = new List<Data>
{
	new Data { Country = "India", Capital = "New Delhi"},
	new Data { Country = "South Africa", Capital = "Cape Town"},
	new Data { Country = "Nigeria", Capital = "Abuja" },
	new Data { Country = "Singapore", Capital = "Singapore" }
};
```

**3.** Add the Data class:

```C#
public class Data
{
	public string Country { get; set; }
	public string Capital { get; set; }
}

```

**4.** Add `TapGestureRecognizer` for right-click and get the position of the internal ScrollView in the DataGrid on right click and use the DataGrid `HitTestService.CellInfoFromPoint()` method , to get the  cell info for the concrete position. 

```C#
RadScrollView sv = null;
foreach (var child in this.dataGrid)
{
	if (child is RadScrollView)
	{
		sv = child as RadScrollView;
		break;
	}
}

var content = sv.Content;

var tap = new TapGestureRecognizer()
{
	Buttons = ButtonsMask.Secondary
};

tap.Tapped += (s, e) =>
{
	var position = e.GetPosition(content);
	var hitTestService = this.dataGrid.HitTestService;
	var cellInfo = hitTestService.CellInfoFromPoint(position.Value);

	// sample visualization the data in the cell when right-click
	App.Current.MainPage.DisplayAlert("Right click on",""+cellInfo.Value,"ОК");
};

```

**5.** Finally, add this gesture to the DataGrid `GestureRecognizers`.

```C#
this.dataGrid.GestureRecognizers.Add(tap);
```