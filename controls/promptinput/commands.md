---
title: Commands
page_title: .NET MAUI PromptInput Documentation - Commands
description: Learn which commands the Telerik UI for .NET MAUI PromptInput exposes and how to use them to handle sending messages, attaching files, and more.
position: 8
slug: promptinput-commands
---

# .NET MAUI PromptInput Commands

The Telerik UI for .NET MAUI PromptInput control exposes a number of commands for notifying after user interactions such as sending messages, attaching files or photos, removing attached files, and handling speech recognition.

The PromptInput supports the following commands:

* `SendMessageCommand` (`ICommand`)&mdash;Executed when a message is sent, either when the Send Message button is pressed or when the Enter key is pressed. The command parameter is of type `object` and its value matches the value of the `Message` property.
* `PickFileCommand` (`ICommand`)&mdash;Opens the `Microsoft.Maui.Storage.FilePicker` so the end user can attach files for upload.
* `PickPhotoCommand` (`ICommand`)&mdash;Opens the `Microsoft.Maui.Media.MediaPicker` so the end user can attach photos for upload.
* `TakePhotoCommand` (`ICommand`)&mdash;Opens the device camera so the end user can capture and attach a photo.
* `RemoveAttachedFileCommand` (`ICommand`)&mdash;Executed when an attached file is removed from the PromptInput.
* `SpeechRecognizedCommand` (`ICommand`)&mdash;Executed when speech is recognized by the Speech-to-Text button.

## See Also

- [Getting Started]({%slug promptinput-getting-started%})
- [Configuration]({%slug promptinput-configuration%})
- [Affix Content]({%slug promptinput-affix-content%})
- [Styling]({%slug promptinput-styling%})
