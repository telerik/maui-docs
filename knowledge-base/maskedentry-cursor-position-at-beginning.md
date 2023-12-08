---
title: Apply MaskedEntry Cursor Position at the Beginning
description: Set cursor position at the beginning of the control
type: how-to
page_title: MaskedEntry for .NET MAUI with cursor position on focus
slug: maskedentry-cursor-position-at-beginning
position: 
tags: maui, visual studio, official, masked, entry, cursor
ticketid: 1623597
res_type: kb
---

## Environment
<table>
    <tbody>
        <tr>
            <td>Product Version</td>
            <td>6.1.0</td>
        </tr>
        <tr>
            <td>Product</td>
            <td>MaskedEntry for .NET MAUI</td>
        </tr>
    </tbody>
</table>


## Description

This article shows how to set the `CursorPosition` property of the MaskedEntry control when the control receives Focus.

## Solution

You need to define a MaskedEntry and when control receives focus, implement the logic to set the `CursorPosition` at the beginning of the text. Here is the code:

**1.** MaskedEntry definition in XAML:

```
<telerik:RadTextMaskedEntry Focused="RadTextMaskedEntry_Focused" Mask="#####" FontSize="26" x:Name="mask"/>
```

**2.** Focused event handler implementation:

```C#
private void RadTextMaskedEntry_Focused(object sender, FocusEventArgs e)
    {
        if (IsMaskEmpty(this.mask.Text))
        {
            RadEntry entry = ChildrenOfType<RadEntry>(this.mask).FirstOrDefault();
            if (entry != null)
            {
                this.mask.Dispatcher.DispatchDelayed(TimeSpan.FromSeconds(0.01), () =>
                {
#if IOS
                entry.CursorPosition = 1;                            
#endif
                    entry.CursorPosition = 0;
                });
            }
        }
    }

    private static IEnumerable<T> ChildrenOfType<T>(IView view)
    where T : IView
    {
        if (view is T t)
        {
            yield return t;
        }

        if (view is Layout layout)
        {
            foreach (var child in layout.Children)
            {
                foreach (var tChild in ChildrenOfType<T>(child))
                {
                    yield return tChild;
                }
            }
        }
    }

    private static bool IsMaskEmpty(string text)
    {
        foreach (var ch in text)
        {
            if (ch != '_')
            {
                return false;
            }
        }

        return true;
    }
```
