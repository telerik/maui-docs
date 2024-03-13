---
title: Commands
page_title: .NET MAUI DataForm Documentation - Commands
description: Learn more about the commands in the Telerik UI .NET MAUI DataForm control.
position: 11
slug: dataform-commands
---

# .NET MAUI DataForm Commands

Telerik UI for .NET MAUI DataForm exposes a number of commands that execute the validation logic, commit all pending changes and cancel the pending changes.

* `ValidateCommand`(`ICommand`)&mdash;Gets a command to execute the validation logic of the `RadDataForm`. This command is useful when the DataForm `ValidationMode` property is `Explicit`. For more details review the [Validation]({%slug dataform-validation%}) article.
* `CommitCommand`(`ICommand`)&mdash;Gets a command to commit all pending changes in the `RadDataForm`. This command is useful when the DataForm `CommitMode` property is `Explicit`. For more details review the [Commit Data]({%slug dataform-commit-data%}) article.
* `CancelCommand`(`ICommand`)&mdash;Gets a command to cancel all pending changes in the `RadDataForm`. This command is useful when the DataForm `CommitMode` property is `Explicit`.

## See Also

- [Editors]({%slug dataform-editors%})
- [Grouping]({%slug dataform-grouping%})
- [Headers]({%slug dataform-headers%})
- [Layouts]({%slug dataform-layouts%})
- [Commit Data]({%slug dataform-commit-data%})