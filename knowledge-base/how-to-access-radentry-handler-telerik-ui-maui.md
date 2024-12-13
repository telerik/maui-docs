---
title: Accessing RadEntry Handler in Telerik UI for MAUI 8.0.0
description: Learn how to access the RadEntry handler in Telerik UI for MAUI version 8.0.0 after the breaking changes introduced in the latest update.
type: how-to
page_title: How to Access RadEntry Handler in Telerik UI for MAUI After Update to 8.0.0
slug: how-to-access-radentry-handler-telerik-ui-maui
tags: maui, radentry, handler, platformview, loaded event, radtextinput
res_type: kb
ticketid: 1673301
---

## Description
In Telerik UI for MAUI 7.1.0, it was possible to access the `RadEntry` handler and perform custom logic by subscribing to the `HandlerChanged` event. After updating to Telerik UI for MAUI 8.0.0, this approach does not work due to [breaking changes](https://docs.telerik.com/devtools/maui/upgrade/breaking-changes/8-0-0#entry) associated with the control's refactoring. This refactoring was part of the new Telerik theming mechanism. This knowledge base article also answers the following questions:
- How do I modify the `RadEntry` handler in Telerik UI for MAUI 8.0.0?
- What is the new way to access the `RadEntry` platform-specific view in the latest version?
- How can I apply custom logic to the `RadEntry` control after the 8.0.0 update?

## Environment
| Version | Product | Author | 
| --- | --- | ---- | 
| 8.0.0 | Telerik UI for .NET MAUI Entry| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Solution
To access the `RadEntry` handler in Telerik UI for MAUI 8.0.0, subscribe to the `Loaded` event of the `RadEntry`. In the event handler, obtain the `RadTextInput` control, which is used in the `RadEntry` template. Then, subscribe to the `RadTextInput.HandlerChanged` event and implement the necessary logic there.

**1.** Subscribe to the `Loaded` event of `RadEntry`.

```csharp
myEntry.Loaded += OnEntryLoaded;
```

**2.** In the `OnEntryLoaded` method, get the `RadTextInput` control from the `RadEntry` template.

```csharp
private void OnEntryLoaded(object sender, EventArgs e)
{
var textInput = ChildOfType<RadTextInput>(this.entry);
if (textInput != null)
{
    var handler = textInput.Handler;
    if (handler == null)
    {
        textInput.HandlerChanged += this.OnTextInputHandlerChanged;
    }
    else
    {
        this.UpdateNativeElement(handler);
    }
}
}

internal static T ChildOfType<T>(View visualElement) where T : View
{
    if (visualElement == null)
    {
        return null;
    }

    foreach (var item in VisualTreeElementExtensions.GetVisualTreeDescendants(visualElement))
    {
        if (item is T targetElement)
        {
            return targetElement;
        }
    }

    return null;
}
```

**3.** Implement the `UpdateNativeElement` method to add your custom logic.

```csharp
private void OnTextInputHandlerChanged(object sender, EventArgs e)
{
    var textInput = (RadTextInput)sender;

    this.UpdateNativeElement(textInput.Handler);

    textInput.HandlerChanged -= this.OnTextInputHandlerChanged;
}

private void UpdateNativeElement(IViewHandler handler)
{
    var nativeEntry = handler.PlatformView as Telerik.Maui.Platform.RadMauiTextInput;
    if (nativeEntry != null)
    {
        // add your logic here
    }
}
```

This approach ensures you can access the native platform view and apply custom logic to the `RadEntry` control, adapting to the changes introduced in Telerik UI for MAUI 8.0.0.

## See Also
- [Telerik UI for MAUI Entry - Breaking Changes in 8.0.0](https://docs.telerik.com/devtools/maui/upgrade/breaking-changes/8-0-0#entry)
- [Telerik UI for MAUI Styling and Themes Overview](https://docs.telerik.com/devtools/maui/styling-and-themes/overview)
