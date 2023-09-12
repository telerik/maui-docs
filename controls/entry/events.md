---
title: Events
page_title: .NET MAUI Entry Documentation - Events
description: Learn how to use the exposed events of the Telerik UI for .NET MAUI Entry control.
position: 5
tags: entry, input text, event, .net maui, text changed, enter key, complated event, input control
previous_url: /controls/entry/entry-events
slug: entry-events
---

# .NET MAUI Entry Events

The Telerik UI for .NET MAUI Entry control exposes a number of events and commands for notifying after user interactions.

The Entry supports the following events:

* `TextChanged`&mdash;Occurs when the text is changed. The `TextChanged` event handler receives a `TextChangedEventArgs` argument containing data related to this event. The `TextChangedEventArgs` provides the following properties:
	* `NewTextValue(string)`&mdash;Gets the new text value.
	* `OldTextValue(string)`&mdash;Gets the old text value.

* `Completed`&mdash;Occurs when the user finalizes the text in an entry with the return key.

The following example demonstrates the Entry definition in XAML with the `TextChanged` and `Completed` event handlers.

**1.** Define the Entry.

 ```XAML
<VerticalStackLayout>
    <telerik:RadEntry x:Name="entry"
                      Keyboard="Numeric"
                      WatermarkText="Watermark Text"
                      TextChanged="Entry_TextChanged"
                      Completed="Entry_Completed"/>
    <Label x:Name="textChangedLabel"/>
</VerticalStackLayout>
 ```

**2.** Set the `TexhChanged` event.

```C#
private void Entry_TextChanged(object sender, TextChangedEventArgs e)
{
    this.textChangedLabel.Text = $"Text changed from {e.OldTextValue} to {e.NewTextValue}";
}
```

**3.** Set the `Completed` event.

```C#
private void Entry_Completed(object sender, EventArgs e)
{
    this.textChangedLabel.Text = "User completed entering text";
}
```

## See Also

- [Entry Getting Started]({% slug entry-getting-started%})
- [Entry Styling]({% slug entry-styling%})
