---
title: Configuration
page_title: .NET MAUI PromptInput Documentation - Configuration
description: Learn how to configure the Telerik UI for .NET MAUI PromptInput control by setting the input message, placeholder, display mode, max input lines, buttons visibility, and more.
position: 5
slug: promptinput-configuration
---

# .NET MAUI PromptInput Configuration

The PromptInput provides a number of settings for configuring the way its input area, built-in buttons, and attached files are displayed and behave.

## Setting the Message

The PromptInput exposes the `Message` (`object`) property which gets or sets the message that is typed in the input area. You can bind the `Message` property to a view-model property and use it to retrieve the current value of the input.

## Adding Placeholder

The PromptInput exposes the `Placeholder` (`string`) property that prompts the user what information is expected in the input area. The placeholder text is displayed when the control is empty.

The following example demonstrates how to set the `Placeholder` property:

```XAML
<telerik:RadPromptInput Placeholder="Type a prompt" />
```

>tip For customizing the color of the input text and the placeholder text, see the [Styling the Prompt Text]({%slug promptinput-styling%}#styling-the-prompt-text) section of the Styling article.

## Setting the Display Mode

The `DisplayMode` (`Telerik.Maui.Controls.PromptInput.PromptInputDisplayMode`) property allows you to control how the PromptInput is rendered. The property accepts the following values:

* (Default) `Automatic`&mdash;The control automatically chooses the most appropriate layout depending on the available space.
* `Compact`&mdash;The control renders in a compact single-line layout with all elements displayed in a single-line.
* `Expanded`&mdash;The control renders in an expanded multi-line layout.

The following example demonstrates how to set the `DisplayMode` property to `Automatic`:

<snippet id='promptinput-displaymode-automatic-xaml' />

The following example demonstrates how to set the `DisplayMode` property to `Compact`:

<snippet id='promptinput-displaymode-compact-xaml' />

The following example demonstrates how to set the `DisplayMode` property to `Expanded`:

<snippet id='promptinput-displaymode-expanded-xaml' />

> For runnable examples demonstrating the PromptInput DisplayMode options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **PromptInput > Features** category.

## Defining the Max Input Lines

The `MaxInputLines` (`int`) property allows you to set the maximum number of lines the text input area displays before it becomes scrollable. The default value is `5`. When the `DisplayMode` is set to `Compact`, the input area is always rendered on a single line regardless of this value.

The following example demonstrates how to set the `MaxInputLines` property:

<snippet id='promptinput-maxinputlines-xaml' />

>tip For a runnable example demonstrating the PromptInput MaxInputLines property, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **PromptInput > Features** category.

## Controlling the Buttons Visibility

The PromptInput exposes the following properties that control the visibility of its built-in buttons:

* `IsMoreButtonVisible` (`bool`)&mdash;Specifies whether the 'More' button is visible in the input area. When visible, the button provides access to additional actions, such as attaching files or photos. The default value is `true`.
* `IsSpeechToTextButtonVisible` (`bool`)&mdash;Specifies whether the Speech-to-Text button is visible in the input area. When visible, end users can dictate their messages through speech recognition. The default value is `true`.

The following example demonstrates how to control the visibility of the built-in buttons:

<snippet id='promptinput-buttons-visibility' />

## Configuring the Send Message Button

The `SendMessageButtonImage` (`ImageSource`) property allows you to set a custom image for the Send Message button.

```XAML
<telerik:RadPromptInput SendMessageButtonImage="send_icon.png" />
```

## Configuring the More Button Actions

The 'More' button can display a collection of custom actions. The PromptInput exposes the following properties for configuring them:

* `MoreButtonActions` (`IList<PromptInputButtonAction>`)&mdash;Defines the collection of toolbar actions displayed in the **More** button.
* `AutoGenerateMoreButtonActions` (`bool`)&mdash;Defines a value indicating whether default actions for the **More** button are automatically generated. The default value is `true`.

## Managing the Attached Files

The PromptInput displays the currently attached files that have not been sent yet through the `AttachedFiles` (`ICollection<PromptInputAttachedFile>`) property.

The `PickFileTypes` (`FilePickerFileType`) property allows you to specify the type of files that can be attached through the UI displayed when the end user taps the attach-files action.

>tip For runnable examples demonstrating the PromptInput Configuration options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **PromptInput > Features** category.

## See Also

- [Commands]({%slug promptinput-commands%})
- [Affix Content]({%slug promptinput-affix-content%})
- [Styling]({%slug promptinput-styling%})
