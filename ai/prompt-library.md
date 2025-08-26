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

<div style="display: grid; gap: 10px; grid-template-columns: 1fr 1fr;">

```prompt Setup New Project and Add DataGrid control
#telerik-maui-assistant Create new maui project with Telerik. Add sample usage of the DataGrid component.
```
```ts
```
```prompt Component Overview
#telerik-maui-assistant What are the main Telerik UI for Maui components and their primary use cases?
```
```ts
```
```prompt Create Project with Telerik Dark Theme
#telerik-maui-assistant Add Theming to my project and set the theme to PlatformDark.
```
```ts
```

</div>

## Component-Specific Prompts

This section provides examples of prompts targeting specific Telerik UI for MAUI components.

### DataGrid


<div style="display: grid; gap: 10px; grid-template-columns: 1fr 1fr;">

```prompt DataGrid with Sample Data
#telerik-maui-assistant Create a DataGrid with 3 columns - Name, Country, City. Add the corresponding business object in the code behind and populate it with sample data. Add 20 entries to the data.
```
```ts
```
```prompt DataGrid with Sorting, Grouping and Aggregates
#telerik-maui-assistant Create a data grid with 100 records each having Id, Name and Company. Group the data by Company. Sort by name. Add aggregate count function for the company column.
```
```ts
```

```prompt DataGrid with ComboBox Column
#telerik-maui-assistant Data bind the DataGrid control to a collection of items. Add columns for stock data manually where one of the columns should use a ComboBox.
```
```ts
```

```prompt DataGrid with Paging
#telerik-maui-assistant Create a DataGrid with 100 employee records with two columns for name and company name. Include paging in the DataGrid with 20 records per page.
```
```ts
```

```prompt DataGrid with Frozen Column, Filtering and Disabled Sorting and Editing
#telerik-maui-assistant Create a DataGrid with 3 columns - Name, Country, City. Add sample data from ViewModel. I would like the Name column to be frozen, the Country and City should not be editable. Allow filtering only for Name and disable sorting for all columns.
```
```ts
```

```prompt DataGrid with Load on Demand and Multiple Selection
#telerik-maui-assistant Add DataGrid with initially 5 items. New 10 items should be loaded on demand. Enable multiple selection of cells.
```
```ts
```

</div>

### CollectionView

<div style="display: grid; gap: 10px; grid-template-columns: 1fr 1fr;">

```prompt CollectionView with Drag and Drop
#telerik-maui-assistant Add CollectionView. Enable drag and drop operation in the control.
```
```ts
```

```prompt CollectionView with Grouping and Sorting
#telerik-maui-assistant Add CollectionView for countries bound to 500 items in the view model. Sort the data by date founded property and group the data by continent. Apply styling to the countries.
```
```ts
```

```prompt collectionView with Custom DataTemplate and Preselected Item
#telerik-maui-assistant Add an example with the control bound to a collection of 200 items. The items should contain name, address, city and id. Preselect the second item and apply custom ui for the items. The UI should also include an image and a checkbox. 
```
```ts
```

```prompt CollectionView with Grouping, Sticky Headers, Filtering and Footer
#telerik-maui-assistant Add CollectionView with 50 countries, show the country in the collectionview and group by continent. Enable sticky groups and add info in the headers how many items are in each group. Add UI in the header of the collectionview for filtering by country. In the footer add the count of all countries.
```
```ts
```

</div>

### ComboBox

<div style="display: grid; gap: 10px; grid-template-columns: 1fr 1fr;">

```prompt ComboBox with Sample Data
#telerik-maui-assistant Add ComboBox data bound to a collection of business objects. Each object should have a Name, Address, City and Country property. Use the Name to display the items in the UI.
```
```ts
```

```prompt ComboBox with Multiple Selection and Custom DataTemplate
#telerik-maui-assistant Add ComboBox data bound to a collection of business objects. Each object should have a Name, Address, City and Country property. Use the Name to display the items in the UI. Show all of the properties in the drop down and allow multiple selection.
```
```ts
```

```prompt ComboBox with Multiple Selection and Open Dropdown on Selection
#telerik-maui-assistant Add ComboBox with 30 countries. Allow multiple selection and prevent the dropdown from closing on selection. Set the placeholder to "Select Country".
```
```ts
```

</div>

### Chart

<div style="display: grid; gap: 10px; grid-template-columns: 1fr 1fr;">

```prompt Line Chart with Sample Data
#telerik-maui-assistant Create a line chart with 100 records of sample data. Each record should have Value plotted on the vertical axis and Date on the horizontal axis.
```
```ts
```

```prompt Chart with Bar and Line Series
#telerik-maui-assistant Create a chart with mixed series visualization - bar, line and point. Each item should have a category representing a quarter (Q1, Q2, etc.) and a numeric value representing the sales for the quarter in US dollars.
```
```ts
```

```prompt Chart with Pan, Zoom and Tooltips features
#telerik-maui-assistant Add Bar Chart with sample data. Apply horizontal zooming, enable panning and show tooltips.
```
```ts
```

</div>

### TabView

<div style="display: grid; gap: 10px; grid-template-columns: 1fr 1fr;">

```prompt TabView with 3 Tabs and Preselected Second Tab
#telerik-maui-assistant Create TabView with 3 tabs and preselect the second tab. First tab should have a CollectionView as content, second tab should have a detail view for stocks, third tab should have a pie chart.
```
```ts
```

```prompt TabView with Custom Header Item Template
#telerik-maui-assistant Create a TabView with custom templates for header items. The header item template should have a label for displaying icons, text and a delete button (removing the tab).
```
```ts
```

```prompt Add Tabs Dynamically
#telerik-maui-assistant Add TabView with 2 items. Provide a button at the bottom right corner of the page for adding items. When the button is clicked add new items.
```
```ts
```

</div>

### Scheduler

<div style="display: grid; gap: 10px; grid-template-columns: 1fr 1fr;">

```prompt Scheduler with All Views
#telerik-maui-assistant Define a scheduler with all available views. By default show week view. Create sample appointments visible in the current week for Monday and Friday. Use ViewModel for the appointments source.
```
```ts
```

</div>

## See Also 

* [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
* [GitHub Copilot Tutorials](https://github.com/features/copilot/tutorials)
* [Telerik MAUI MCP Server]({%slug ai-mcp-server%})
* [Telerik UI for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui/)

<style>
.d-print-none button:nth-child(2) {
  display: none !important;
}
</style>