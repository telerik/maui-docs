---
title: Highlighting the Text in the DataGrid through Search Entry
page_title: Searching and Highlighting the Result in the DataGrid Cells - .NET MAUI Knowledge Base
description: Learn how to highlight the text in the cells of the Telerik UI for .NET MAUI DataGrid component through the Search entry when searching from an external UI.
type: how-to
slug: datagrid-cell-text-highlight
tags: maui, datagrid, ui for maui, highlight search result, text highlight
ticketid: 1582978
res_type: kb
---

## Environment

<table>
	<tbody>
    <tr>
      <td>Product</td>
      <td>Telerik UI for .NET MAUI DataGrid</td>
    </tr>
  	<tr>
  		<td>Product Version</td>
  		<td>3.2.1</td>
  	</tr>
	</tbody>
</table>

## Description

How can I highlight a chunk of text inside a Telerik UI for .NET MAUI DataGrid cell when searching from an external UI?

## Solution

Generally, to achieve the desired scenario, use a Telerik UI for .NET MAUI Entry control for the Searching UI.

To highlight the text in the DataGrid, use a `CellTemplateColumn` and add a `RadHighlightLabel` in it. Then, set the `UnformattedText`, `HighlightText`, and `HighlightTextColor` properties of the `RadHighlight` label to get the following result:

![DataGrid Highlighted Text](images/highlightedtext.png)

By binding the `HighlightText` property to the text value of the Entry you will be able to get the characters which need to be highlighted. The `UnformattedText` property must be bound to the `ItemsSource` propertys.

The following example shows the implementation the suggested approach.

```XAML
<telerik:RadEntry x:Name="searchEntry"
				  HeightRequest="50"
				  WidthRequest="300"
				  Placeholder="Search Entry"/>
<telerik:RadDataGrid x:Name="dataGrid" AutomationId="dataGrid" AutoGenerateColumns="False">
	<telerik:RadDataGrid.Columns>
		<telerik:DataGridTextColumn PropertyName="Country" HeaderText="HighlightedLabel">
			<telerik:DataGridTextColumn.CellContentTemplate>
				<DataTemplate>
					<telerik:RadHighlightLabel UnformattedText="{Binding Country}"
											   HighlightText="{Binding Source={x:Reference searchEntry}, Path=Text}"
											   HighlightTextColor="Red"/>
				</DataTemplate>
			</telerik:DataGridTextColumn.CellContentTemplate>
		</telerik:DataGridTextColumn>
	</telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```
