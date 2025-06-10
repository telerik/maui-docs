---
title: Creating a Copyright Label Control in .NET MAUI
description: Learn how to create a Copyright label control using the Label with formatted spans in .NET MAUI application.
type: how-to
page_title: How to Use Label with Formatted Spans for a Copyright Control in .NET MAUI
slug: create-copyright-label-control-dotnet-maui
tags: label, copyright, formattedtext, span, gesture
res_type: kb
---

## Environment

| Product | Author | 
| --- | ---- | 
| .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to know how to create a Copyright label control for my application using .NET MAUI. I need the control to display the copyright symbol followed by a year and some text, with custom text color, underlining, and tap gesture recognizers for handling user interactions.

This knowledge base article also answers the following questions:
- How to format text in a Label using spans in .NET MAUI?
- How to add tap gesture recognizers to a Label in .NET MAUI app?
- How to underline and set text colors for individual spans in .NET MAUI?

## Solution

To create a Copyright label control, use the `Label` control with formatted text consisting of multiple spans. Below is the implementation:

```xaml
<Label>
    <Label.FormattedText>
        <FormattedString>
            <!-- Display the copyright symbol -->
            <Span Text="&#169;" />

            <!-- Display the copyright year and text with custom styling -->
            <Span Text="Copyright 2025"
                  TextColor="Blue"
                  TextDecorations="Underline">
                <!-- Add a tap gesture recognizer -->
                <Span.GestureRecognizers>
                    <TapGestureRecognizer Command="{Binding TapCommand}" />
                </Span.GestureRecognizers>
            </Span>
        </FormattedString>
    </Label.FormattedText>
</Label>
```

1. The `Span` inside `FormattedString` allows you to define segments of text with different styles and behaviors.
2. The copyright symbol (`&#169;`) is defined as a separate `Span`.
3. Another `Span` is used for the "Copyright 2025" text, with `TextColor` set to `Blue` and `TextDecorations` set to `Underline`.
4. A `TapGestureRecognizer` is added to the second `Span` to handle user interactions. Bind it to a command in the view model using `{Binding TapCommand}`.

## See Also

- [Label Documentation for .NET MAUI](https://docs.microsoft.com/en-us/dotnet/maui/user-interface/controls/label)
- [FormattedString Documentation](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/label?view=net-maui-9.0#use-formatted-text)
- [Gesture Recognizers in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/gestures/tap?view=net-maui-9.0)
