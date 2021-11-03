---
title: Events
page_title: .NET MAUI Entry Documentation | Events
description: "Use the exposed events of the Telerik UI for .NET MAUI Entry control."
position: 5
slug: entry-events
---

# Events

The Telerik UI for .NET MAUI Entry control exposes a number of events and commands for handling its behavior.

The supported events of the Entry are:

* **TextChanged**&mdash;Occurs when the text is changed. The `TextChanged` event handler receives a `TextChangedEventArgs` argument containing data related to this event. The `TextChangedEventArgs` provides the following properties:
	* NewTextValue*(string)*&mdash;Gets the new text value.
	* OldTextValue*(string)*&mdash;Gets the old text value.

* **Completed**&mdash;Occurs when the user finalizes the text in an entry with the return key.

For its **Completed** event, the Entry exposes the **CompletedCommand**(*ICommand*) command.

The following example demonstrates the Entry definition in XAML with the `TextChanged` and `Completed` event handlers.

```XAML
<StackLayout>
    <telerikInput:RadEntry x:Name="entry"
                           Keyboard="Numeric"
                           WatermarkText="Watermark Text"
                           TextChanged="Entry_TextChanged"
                           Completed="Entry_Completed"/>
    <Label x:Name="textChangedLabel"/>
</StackLayout>
```

Here is a sample implementation of the `TexhChanged` event.

```C#
private void Entry_TextChanged(object sender, TextChangedEventArgs e)
{
    this.textChangedLabel.Text = $"Text changed from {e.OldTextValue} to {e.NewTextValue}";
}
```

Here is a sample implementation of the `Completed` event.

```C#
private void Entry_Completed(object sender, EventArgs e)
{
    this.textChangedLabel.Text = "User completed entering text";
}
```

## See Also

- [Entry Getting Started]({% slug entry-getting-started%})
- [Entry Styling]({% slug entry-styling%})
