---
title: Integration with External UI
page_title: Integrating .NET MAUI SmartPasteButton with External UI
description: Learn how to integrate the Telerik SmartPasteButton for .NET MAUI with external UI components to enhance user experience.
position: 2
slug: smartpastebutton-external-ui-integration
---

# .NET MAUI SmartPasteButton Integration with External UI

The SmartPasteButton control can be integrated with external UI components to enhance the user experience and provide additional functionality. For example, you can integrate the SmartPasteButton with a custom form or layout to allow users to populate fields with structured data extracted from unstructured text.

To integrate the SmartPasteButton with external UI components, you have to implement the `ISmartPasteButtonProvider` interface in the external UI component that will provide the fields and handle value assignment for the smart paste operation. Then, you need to set the `Provider` property of the SmartPasteButton to reference the external UI.

The `ISmartPasteButtonProvider` implements the following methods:

* `IEnumerable<SmartPasteButtonField> GetFields()`&mdash;Returns a list of `SmartPasteButtonField` objects that represent the fields that will be used for the smart paste operation.
* `void SetFieldValue(string field, object value)`&mdash;Assigns an extracted value to the field identified by field. The method is called after the AI service has processed the clipboard content and produced a typed result for each field.

The `SmartPasteButtonField` class has the following properties:

* `Field` (`string`)&mdash;Specifies the unique identifier of the field, typically the property name in the underlying data model (for example `"FirstName", "Email"`). This value is used to map extracted results back to the originating field via `Telerik.Maui.Controls.SmartPasteButton.ISmartPasteButtonProvider.SetFieldValue(System.String,System.Object)`.
* `Description` (`string`)&mdash;Specifies a human-readable label that describes the field (for example "First Name", "Email Address"). The AI service uses this description as context when matching clipboard content to the appropriate field.
* `AllowedValues` (`string[]`)&mdash;Specifies the collection of valid values the field can accept. When set, the AI service is constrained to return only one of these values (for example `["Active", "Inactive"]` for a status enum)
* `Type` (`string`)&mdash;Specifies the full CLR type name of the field (for example `"System.String", "System.DateTime", "System.Double"`). This is used to deserialize the AI response into the correct .NET type before the value is assigned to the field.
* `FieldType` (`Type`)&mdash;Specifies the CLR `System.Type` of the field. When set, this takes precedence over the string-based `Telerik.Maui.Controls.SmartPasteButton.SmartPasteButtonField.Type` property for deserializing the AI response into the correct .NET type.

## Example

This is an example of how to integrate the SmartPasteButton with an external UI form:

**1.** Define the editors on the page with two buttons: one for copying the text to the clipboard and another one for the smart paste operation:

<snippet id='smartpastebutton-external-editor' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define a `ViewModel` that implements the `ISmartPasteButtonProvider` interface for the fields that will be used by the SmartPasteButton, and the `SmartPasteRequestCommand` and `CopyToClipboardCommand`:

<snippet id='smartpaste-viewmodel-external' />

This is the result on Android:

![.NET MAUI SmartPasteButton External UI](../images/smartpastebutton-external-ui.gif)

>important The SmartPasteButton examples in the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) use a Telerik-hosted AI service for demonstration purposes only. 
>
>To use the smart paste functionality in your application, you must configure your own AI service.
>
>How to do that is described in the [Configuration]({%slug smartpastebutton-configuration%}) article.

> For a runnable example with the SmartPasteButton with External UI scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **SmartPasteButton > ExternalEditor** category.

## See Also

- [Styling the SmartPasteButton]({%slug smartpastebutton-styling%})
- [Visual States of the SmartPasteButton]({%slug smartpastebutton-visual-states%})
- [Events of the SmartPasteButton]({%slug smartpastebutton-events%})
- [Configure the SmartPasteButton]({%slug smartpastebutton-configuration%})

