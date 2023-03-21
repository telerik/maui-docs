---
title: Commands
page_title: .NET MAUI DataForm Documentation - Commands
description: "Check our &quot;Commands&quot; documentation article for Telerik DataForm for .NET MAUI control."
position: 11
slug: dataform-commands
---

# .NET MAUI DataForm Commands

Telerik UI for .NET MAUI DataForm exposes a number of commands that execute the validation logic, commit all pending changes and cancel the pending changes.

* `ValidateCommand`(`ICommand`)&mdash;Gets a command to execute the validation logic of the RadDataForm. This command is mostly useful when the DataForm `ValidationMode` property is set to `Explicit`. For more details review the [Validation]({%slug dataform-validation%}) article.
* `CommitCommand`(`ICommand`)&mdash;Gets a command to commit all pending changes in the RadDataForm. This command is mostly useful when the DataForm `CommitMode` property is set to `Explicit`. For more details review the [Commit Data]({%slug dataform-commit-data%}) article.
* `CancelCommand`(`ICommand`)&mdash;Gets a command to cancel all pending changes in the RadDataForm. This command is mostly useful when the DataForm `CommitMode` property is set to `Explicit`.
     

## See Also

- [Editors]({%slug dataform-editors%})
- [Grouping]({%slug dataform-grouping%})
- [Headers]({%slug dataform-headers%})
- [Layouts]({%slug dataform-layouts%})
- [Commit Data]({%slug dataform-commit-data%})