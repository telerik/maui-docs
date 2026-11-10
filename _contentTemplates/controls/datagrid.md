#datagrid-keyboard-navigation
## Keyboard Navigation When Editing Cells

When entering the data grid edit mode, the keyboard navigation is different from the navigation when the data grid is in read-only mode. The following table summarizes the keyboard navigation when editing cells:

| Column Type | Editor | Keyboard Navigation | Details |
| --- | --- | --- | --- |
| Boolean | `CheckBox` | To change the state of the checkbox cell, use the `Space` key. | - |
| Date | `RadDatePicker` | To open the picker drop-down use the `Space` key. To select a date, use the `Enter` key. | [DatePicker Keyboard Navigation](%slug datepicker-keyboard-support%) |
| Time | `RadTimePicker` | To open the picker drop-down use the `Space` key. To select a time, use the `Enter` key. | [TimePicker Keyboard Navigation](%slug timepicker-keyboard-support%) |
| ComboBox | `RadComboBox` | To open the combobox drop-down use the `Enter` key. | [ComboBox Keyboard Navigation](%slug combobox-keyboard-support%) |

#end

#datagrid-pull-to-refresh
## How the Integration Works

Wrap the `RadDataGrid` in the `RadRefreshView` as its content. When the user pulls the grid past the pulling threshold and releases it, the RefreshView starts a refresh and executes its `Command`.

To connect the RefreshView to your view model, bind the following properties:

* `Command` (`ICommand`)&mdash;Executes the view model logic that reloads the rows.
* `IsRefreshing` (`bool`)&mdash;Reflects whether a refresh is in progress. The view model sets the property to `false` when the rows are loaded to end the refresh.

For more information about the command properties, see [RefreshView Commands]({% slug refreshview-commands %}).

## Refresh the DataGrid Rows

The following example demonstrates how to use the RefreshView with the DataGrid.

1. Define the RefreshView and the DataGrid in XAML:

    <snippet id='refreshview-integration-datagrid' />

2. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

3. Define the `ViewModel` with the items, the `IsRefreshing` property, and the `RefreshCommand`:

    <snippet id='refreshview-integration-viewmodel' />

4. Define the `Customer` business object:

    <snippet id='refreshview-integration-customer' />

> tip For a runnable example with the RefreshView Integration with DataGrid scenario, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **RefreshView > Integration** category.

## See Also

- [RefreshView Integration with CollectionView]({% slug refreshview-collectionview %})
- [RefreshView Commands]({% slug refreshview-commands %})
- [Refresh State]({% slug refreshview-refresh-state %})
- [DataGrid Overview]({% slug datagrid-overview %})
#end