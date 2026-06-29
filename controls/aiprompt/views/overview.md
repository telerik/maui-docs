---
title: Overview
page_title: .NET MAUI AIPrompt Documentation - Views
description: Learn more about the available views in the Telerik UI for .NET MAUI AIPrompt control.
position: 0
slug: aiprompt-views-overview
---

# Views Overview 

The AIPrompt component provides three predefined views and also lets you create custom views. Only one of these views is displayed at a time, and the user can switch the views via the TabView headers at the top.

The available built-in views are:

- [Input View]({%slug aiprompt-input-view%})&mdash;Displays the input area of the AIPrompt.
- [Output View]({%slug aiprompt-output-view %})&mdash;Displays the output area of the AIPrompt.
- [Commands View]({%slug aiprompt-commands-view %})&mdash;Displays a list of custom AIPrompt commands.

## Define the Views 

You can use two approaches for defining the views depending on the `AutoGenerateViews` property.

* `AutoGenerateViews` (`bool`)&mdash;Indicates whether the AIPrompt views will be auto-generated. Its default value is `True`.
* `SelectedIndex` (`int`)&mdash;Specifies the currently active view. Use it to switch between the Input, Output, and Commands views programmatically or through two-way binding.

### Automatic Views Generation

By default, the .NET MAUI AIPrompt component will always render both the Input and the Output views. The Commands view will be rendered only if you pass a custom set of commands through the `Commands` property.

When the built-in views are auto-generated, the selected tab follows the order of the generated `Views` collection. This lets you set `SelectedIndex` to activate the Input, Output, or Commands view from your view model.

### Manual Views Generation

To manually define the views, set `AutoGenerateViews` to `False` and add the views to the AIPrompt control:

<snippet id='aiprompt-manual-views-xaml' />

Here is a sample `ViewModel` class used in the example:

<snippet id='aiprompt-views-viewmodel' />

## Common Properties

Each view that is supported by the AIPrompt extends the `AIPromptView` class. This class exposes the following properties that you can set for each view:

* `ControlTemplate` (`ControlTemplate`)&mdash;Sets the template that defines the visual appearance of the view.
* `HeaderText` (`string`)&mdash;Defines the text that resides in the TabView Header for switching the views.
* `HeaderImageSource` (`ImageSource`)&mdash;Defines the image source that resides in the TabView Header for switching the views.

## See Also

- [Input View]({%slug aiprompt-input-view%})
- [Output View]({%slug aiprompt-output-view %})
- [Commands View]({%slug aiprompt-commands-view %})
