---
title: Text Selection
page_title: .NET MAUI Entry Documentation | Text Selection
description: Check our &quot;Text Selection&quot; documentation article for Telerik Entry for .NET MAUI control.
position: 3
slug: entry-text-selection
---

# Text Selection

The following properties are related to the Entry text selection: 

* **CursorPosition**(*int*) Specifies the starting position of the text selected in the entry.
* **SelectionLength**(*int*) Specifies the number of characters in the current selection in the entry control.

The next snippet shows how both could be applied in order to preselect part of the Text of the Entry when the control receives the focus:

```XAML
<StackLayout Orientation="Horizontal">
    <telerikInput:RadEntry x:Name="selectEntry" 
						   Text="select some text" />
    <telerikInput:RadButton Text="Focus" 
							Clicked="FocusButtonClicked" />
</StackLayout>
```

And the Clicked event handler:

```C#
private void FocusButtonClicked(object sender, System.EventArgs e)
{
    selectEntry.Focus();
    selectEntry.CursorPosition = 7;
    selectEntry.SelectionLength = 9;
}
```

![Entry Text Selection](images/entry_text_selection.png)

## See Also

- [Events]({% slug entry-events%})
- [Styling]({% slug entry-styling%})
