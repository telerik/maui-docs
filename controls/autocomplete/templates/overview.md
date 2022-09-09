---
title: Overview
page_title: .NET MAUI AutoComplete Documentation - Overview
description: Check our &quot;Overview&quot; documentation article for Telerik AutoComplete for .NET MAUI.
position: 1
slug: autocomplete-custom-templates
---

# .NET MAUI AutoComplete Templates

## Overview

If the default templates of the control do not suit your needs, you can easily define a custom template. The available templates for customizing are:

* `NoResultsTemplate`(`DataTemplate`)&mdash;Defines the template visualised when there are no suggestions found.
* `ShowMoreTemplate`(`DataTemplate`) for Tokens Support&mdash;Defines the template used to create show more view when `DisplayMore="Tokens"`.
* `LoadingTemplate`(`DataTemplate`) for [Remote Search]({%slug autocomplete-remote-search%}) functionality&mdash;Defines the loading message in `RemoteSearch state`.
* `TokensTemplate`(`DataTemplate`) for [Tokens Support]({%slug autocomplete-tokens-support%})&mdash;Defines the template used to vizualize the tokens.
* `SuggestionItemTemplate`(`DataTemplate`)&mdash;Defines the template that will be used to create each of the suggestions.
* `SuggestionViewTemplate`(`DataTemplate`)&mdash;Defines the template used to visualize the filtered items.

## Example

### NoResults Template

Here is an example how the NoResults Template could be defined:

```XAML
<telerik:RadAutoComplete.NoResultsTemplate>
    <DataTemplate>
        <Label Text="No match was found for the specific search. Please try again."
                HorizontalOptions="Center"
                VerticalOptions="Center"/>
    </DataTemplate>
</telerik:RadAutoComplete.NoResultsTemplate>
```

### ShowMore Template

XAML definition of ShoWMore Template:

<snippet id='autocomplete-templates-show-more-template-xaml'/>

### Loading Template

XAML definition of the Loading Template:

```XAML
<telerik:RadAutoComplete.LoadingTemplate>
    <DataTemplate>
        <HorizontalStackLayout HorizontalOptions="Center"
                                Margin="0, 20, 0, 20">
            <Label Text="Searching... " 
                    FontSize="16" 
                    TextColor="#8E8E93"/>
            <telerik:RadBusyIndicator x:Name="busyIndicator" 
                                        HeightRequest="24" 
                                        WidthRequest="24"
                                        IsBusy="True"
                                        VerticalOptions="Start"
                                        AnimationContentColor="#8660C5"
                                        AnimationType="Animation9"/>
        </HorizontalStackLayout>
    </DataTemplate>
</telerik:RadAutoComplete.LoadingTemplate>
```

## See Also

