---
title: Prompt Library
page_title: Telerik UI for .NET MAUI Prompt Library
description: Explore the extensive collection of prompts that you can use with the Telerik UI for MAUI AI Coding Assistant.
slug: ai-prompt-library
position: 4
---

# Telerik UI for MAUI Prompt Library

Welcome to the Telerik UI for MAUI Prompt Library.

The prompts provided here are intended and optimized for use with the Telerik UI for MAUI AI Coding Assistant [MCP Server]({%slug ai-mcp-server%}). They can help you kick start your app development and speed up the component configuration process.

This collection of prompts is not exhaustive and the Telerik UI for .NET MAUI team is constantly working on adding more prompts to the library.

>tip [Go straight to the prompts](#general-prompts)

## How to Use the Prompts

All prompts in this library target the [MCP Server]({%slug ai-mcp-server%}) via the `#telerik-maui-assistant` handle. Make sure that you have installed and enabled the MCP Server before attempting to run the prompts.

1. Browse the prompt library to find a prompt that suits your needs.
2. Copy the prompt text (including the `#telerik-maui-assistant` handle).
3. (Optional) Customize the prompt as needed for your specific use case but keep the `#telerik-maui-assistant` handle.<br/>When modifying the prompts, make sure the changes comply with the [recommendations]({%slug ai-overview%}#recommendations) for the AI Coding Assistant.
4. Run the prompt against the [MCP Server]({%slug ai-mcp-server%}).

>warning Always double-check the code and solutions proposed by any AI-powered tool before applying them to your project.

>caption Use with the Copilot Extension

To run the provided prompts in the [Telerik UI for MAUI GitHub Copilot Extension]({%slug ai-copilot-extension%}) (without the MCP Server installed), modify the prompts to use the `@telerikmaui` handle instead.

## General Prompts

This section provides examples of general questions related to Telerik UI for MAUI.

<table>
<tr>
<th>Setup New Project and Add DataGrid control</th>
<th>Component Overview</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Create new maui project with Telerik. Add sample usage of the DataGrid component.
</code></pre>
</td>
<td>
<pre><code>
#telerik-maui-assistant What are the main Telerik UI for Maui components and their primary use cases?
</code></pre>
</td>
</tr>
</table>

<table>
<tr>
<th>Create Project with Telerik Dark Theme</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Add Theming to my project and set the theme to PlatformDark.
</code></pre>
</td>
</tr>
</table>

## Component-Specific Prompts

This section provides examples of prompts targeting specific Telerik UI for MAUI components.

### DataGrid

The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) is a powerful control that allows you to visualize and edit tabular represented data in your .NET MAUI applications.

<table>
<tr>
<th>DataGrid with Sample Data</th>
<th>DataGrid with Sorting, Grouping and Aggregates</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Create a DataGrid with 3 columns - Name, Country, City. Add the corresponding business object in the code behind and populate it with sample data. Add 20 entries to the data.
</code></pre>
</td>
<td>
<pre><code>
#telerik-maui-assistant Create a data grid with 100 records each having Id, Name and Company. Group the data by Company. Sort by name. Add aggregate count function for the company column.
</code></pre>
</td>
</tr>
</table>

<table>
<tr>
<th>DataGrid with ComboBox Column</th>
<th>DataGrid with Paging</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Data bind the DataGrid control to a collection of items. Add columns for stock data manually where one of the columns should use a ComboBox.
</code></pre>
</td>
<td>
<pre><code>
#telerik-maui-assistant Create a DataGrid with 100 employee records with two columns for name and company name. Include paging in the DataGrid with 20 records per page.
</code></pre>
</td>
</tr>
</table>

<table>
<tr>
<th>DataGrid with Frozen Column, Filtering and Disabled Sorting and Editing</th>
<th>DataGrid with Load on Demand and Multiple Selection</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Create a DataGrid with 3 columns - Name, Country, City. Add sample data from ViewModel. I would like the Name column to be frozen, the Country and City should not be editable. Allow filtering only for Name and disable sorting for all columns.
</code></pre>
</td>
<td>
<pre><code>
#telerik-maui-assistant Add DataGrid with initially 5 items. New 10 items should be loaded on demand. Enable multiple selection of cells.
</code></pre>
</td>
</tr>
</table>

### CollectionView

The [Telerik .NET MAUI CollectionView]({%slug collectionview-overview%}) is a virtualizing view component that provides option to filter, sort and group the items.

<table>
<tr>
<th>CollectionView with Drag and Drop</th>
<th>CollectionView with Grouping and Sorting</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Add CollectionView. Enable drag and drop operation in the control.
</code></pre>
</td>
<td>
<pre><code>
#telerik-maui-assistant Add CollectionView for countries bound to 500 items in the view model. Sort the data by date founded property and group the data by continent. Apply styling to the countries.
</code></pre>
</td>
</tr>
</table>

<table>
<tr>
<th>CollectionView with Custom DataTemplate and Preselected Item</th>
<th>CollectionView with Grouping, Sticky Headers, Filtering and Footer</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Add an example with the control bound to a collection of 200 items. The items should contain name, address, city and id. Preselect the second item and apply custom ui for the items. The UI should also include an image and a checkbox. 
</code></pre>
</td>
<td>
<pre><code>
#telerik-maui-assistant Add CollectionView with 50 countries, show the country in the collectionview and group by continent. Enable sticky groups and add info in the headers how many items are in each group. Add UI in the header of the collectionview for filtering by country. In the footer add the count of all countries.
</code></pre>
</td>
</tr>
</table>

### ComboBox

The [Telerik UI for .NET MAUI ComboBox]({%slug combobox-overview%}) enables users to select one or more items from a dropdown list. 

<table>
<tr>
<th>ComboBox with Sample Data</th>
<th>ComboBox with Multiple Selection and Custom DataTemplate</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Add ComboBox data bound to a collection of business objects. Each object should have a Name, Address, City and Country property. Use the Name to display the items in the UI.
</code></pre>
</td>
<td>
<pre><code>
#telerik-maui-assistant Add ComboBox data bound to a collection of business objects. Each object should have a Name, Address, City and Country property. Use the Name to display the items in the UI. Show all of the properties in the drop down and allow multiple selection.
</code></pre>
</td>
</tr>
</table>

<table>
<tr>
<th>ComboBox with Multiple Selection and Open Dropdown on Selection</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Add ComboBox with 30 countries. Allow multiple selection and prevent the dropdown from closing on selection. Set the placeholder to "Select Country".
</code></pre>
</td>
</tr>
</table>

### Chart

The [Telerik UI for .NET MAUI Charts]({%slug chart-overview%}) are feature-rich, intuitive, and easy-to-use data-visualization controls with differen series like bar, line, pie, financial, etc.

<table>
<tr>
<th>Line Chart with Sample Data</th>
<th>Chart with Bar and Line Series</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Create a line chart with 100 records of sample data. Each record should have Value plotted on the vertical axis and Date on the horizontal axis.
</code></pre>
</td>
<td>
<pre><code>
#telerik-maui-assistant Create a chart with mixed series visualization - bar, line and point. Each item should have a category representing a quarter (Q1, Q2, etc.) and a numeric value representing the sales for the quarter in US dollars.
</code></pre>
</td>
</tr>
</table>

<table>
<tr>
<th>Chart with Pan, Zoom and Tooltips features</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Add Bar Chart with sample data. Apply horizontal zooming, enable panning and show tooltips.
</code></pre>
</td>
</tr>
</table>

### TabView

The [Telerik TabView for .NET MAUI]({%slug tabview-overview%}) is a flexible navigation control that allows you to build tabbed interfaces. 

<table>
<tr>
<th>TabView with 3 Tabs and Preselected Second Tab</th>
<th>TabView with Custom Header Item Template</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Create TabView with 3 tabs and preselect the second tab. First tab should have a CollectionView as content, second tab should have a detail view for stocks, third tab should have a pie chart.
</code></pre>
</td>
<td>
<pre><code>
#telerik-maui-assistant Create a TabView with custom templates for header items. The header item template should have a label for displaying icons, text and a delete button (removing the tab).
</code></pre>
</td>
</tr>
</table>

<table>
<tr>
<th>Add Tabs Dynamically</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Add TabView with 2 items. Provide a button at the bottom right corner of the page for adding items. When the button is clicked add new items.
</code></pre>
</td>
</tr>
</table>

### Scheduler

The [Telerik UI for .NET MAUI Scheduler]({%slug scheduler-overview%}) allows you to easily implement various scheduling scenarios in your .NET MAUI apps.

<table>
<tr>
<th>Scheduler with All Views</th>
</tr>
<tr>  
<td>
<pre><code>
#telerik-maui-assistant Define a scheduler with all available views. By default show week view. Create sample appointments visible in the current week for Monday and Friday. Use ViewModel for the appointments source.
</code></pre>
</td>
</tr>
</table>

## See Also 

* [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
* [GitHub Copilot Tutorials](https://github.com/features/copilot/tutorials)
* [Telerik MAUI MCP Server]({%slug ai-mcp-server%})
* [Telerik UI for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui/)
