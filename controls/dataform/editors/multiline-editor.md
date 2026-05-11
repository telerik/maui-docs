---
title: Multiline Editors
page_title: .NET MAUI DataForm Documentation - Multiline Editors
description: Learn more about the multiline editors that the Telerik UI for .NET MAUI DataForm control provides.
position: 4
slug: dataform-multiline-editors
---

# .NET MAUI DataForm Multiline Editors

You can use the following Multiline Editors the DataForm provides:

* `DataFormRadMultiLineEditor`&mdash;Of type `Telerik .NET MAUI RadEditor`. This is the default editor that renders inside the DataForm when html or multiline text is used as datatype for a property.
* `DataFormMultiLineEditor`&mdash;Of type `.NET MAUI Editor`.

Other properties that are common for all editors are listed in the [Editors Overview]({%slug dataform-editors%}#common-properties) article.

## Styling 

You can style the editors using the properties `BackgroundColor`, `BorderColor` and `BorderThickness`. You can additionally style each editor by applying a style with the same target type as the underlying control.

The target type for the `DataFormRadMultiLineEditor` is `Telerik.Maui.Controls.RadEditor`, while the target type for the `DataFormMultiLineEditor` is `Microsoft.Maui.Controls.Editor`.

For more information about how to style the editors, review the [Editors Styling article]({%slug dataform-editors-styling%}).

## See Also

- [Editors]({%slug dataform-editors%})