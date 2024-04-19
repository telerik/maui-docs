---
title: Setting Font Size for the Text inside the Accordion Header
description: Learn how to set the font size for the text inside the AccordionItemHeader in the Accordion for .NET MAUI.
type: how-to
page_title: Setting Font Size for AccordionItemHeader in Accordion for .NET MAUI
slug: setting-font-size-accordionitemheader-net-maui
tags: accordion, accordionitemheader, font size, .net maui
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.8.0 | Telerik UI for .NET MAUI Accordion| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

I want to set the font size for the text inside the AccordionItemHeader in the Accordion for .NET MAUI.

## Solution

To set the font size for the text inside the `AccordionItemHeader`, you can apply the `FontSize` property directly to the Label element inside the `AccordionItem.Header` element. Here is an example:

```xaml
<telerik:RadAccordion x:Name="accordion">
    <telerik:AccordionItem HeaderText="Attachments">
        <telerik:AccordionItem.Content>
            <Label Text="Attach files" Margin="30" />
        </telerik:AccordionItem.Content>
    </telerik:AccordionItem>
    <telerik:AccordionItem>
        <telerik:AccordionItem.Header>
            <telerik:AccordionItemHeader
                    IndicatorColor="Blue"
                    IndicatorFontSize="16"
                    IndicatorLocation="End"
                    BorderColor="LightBlue"
                    BorderThickness="2">
                <Label Text="Settings" Margin="8" FontSize="20" />
            </telerik:AccordionItemHeader>
        </telerik:AccordionItem.Header>
        <telerik:AccordionItem.Content>
            <Label Text="Add your comment here" Margin="30" />
        </telerik:AccordionItem.Content>
    </telerik:AccordionItem>
    <telerik:AccordionItem HeaderText="Rating" IsExpanded="True">
        <telerik:AccordionItem.Content>
            <telerik:RadShapeRating x:Name="rating" Margin="20"/>
        </telerik:AccordionItem.Content>
    </telerik:AccordionItem>
</telerik:RadAccordion>
```

In the example above, the `FontSize` property of the Label element inside the `AccordionItemHeader` is set to "20" to change the font size of the text. You can adjust the value according to your needs.
