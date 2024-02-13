Through the popup or the drop-down, users can pick an item. This must be confirmed or rejected with the **OK** or **Cancel** buttons located in the popup or drop-down.

The {{page.control_name}} allows you to add a custom logic for the `Accept` and `Cancel` commands which are executed when the **OK** or **Cancel** buttons are clicked.

* `AcceptCommand`(`ICommand`)&mdash;Defines the command, which confirms the current selection of the picker and closes the popup or drop-down. Use the `AcceptCommandParameter` to pass a parameter to the command execute method. 
* `CancelCommand`(`ICommand`)&mdash;Defines the command, which rejects the current selection of the picker and closes the popup or drop-down. Use the `CancelCommandParameter` to pass a parameter to the command execute method.

You can apply the `Accept` and `Cancel` commands for the popup mode by setting the `PopupSettings` property of the {{page.control_name}}. For the drop-down mode, use the `DropDownSettings` property.