---
title: Events
page_title: .NET MAUI Entry Documentation | Events
description: Check our &quot;Events&quot; documentation article for Telerik Entry for .NET MAUI control.
position: 3
slug: entry-events
---

# Events

**RadEntry** exposes the following events:

* **TextChanged**: Occurs when the text is changed. The TextChanged event handler receives a TextChangedEventArgs argument containing data related to this event. The TextChangedEventArgs provides the following properties:
	* NewTextValue*(string)*: which gets the new text value.
	* OldTextValue*(string)*: that gets the old text value.

* **Completed**: Occurs when the user finalizes the text in an entry with the return key.

## Commands

**RadEntry** control exposes **Command** for its Completed event: 

**CompletedCommand**(*ICommand*).

## Example

Here is the RadEntry definition in XAML with the TextChanged and Completed event handlers:

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

Here is a sample implementation of the TexhChanged event:

```C#
private void Entry_TextChanged(object sender, TextChangedEventArgs e)
{
    this.textChangedLabel.Text = $"Text changed from {e.OldTextValue} to {e.NewTextValue}";
}
```

and for the Completed event:

```C#
private void Entry_Completed(object sender, EventArgs e)
{
    this.textChangedLabel.Text = "User completed entering text";
}
```

## See Also

- [Entry Getting Started]({% slug entry-getting-started%})
- [Entry Theming and Style]({% slug entry-theming-style%})
