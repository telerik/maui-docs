---
title: Commands
page_title: .NET MAUI Conversational UI Documentation - Commands
description: Learn how to use the exposed commands of the Telerik UI for .NET MAUI Chat
position: 7
slug: chat-commands
---

# .NET MAUI Chat Commands

The Telerik UI for .NET MAUI Chat allows you to attach commands that will be executed when certain actions occur.

## Commands Related to the Chat Input Area:

* `SendMessageCommand` (`ICommand`)&mdash;Defines the command that is executed when the send button is clicked or the `Enter` key is pressed. 
* `PickFileCommand` (`ICommand`)&mdash;Defines the command that opens the Microsoft.Maui.Storage.FilePicker for attaching files for upload.
* `PickPhotoCommand` (`ICommand`)&mdash;Defines the command that opens the Microsoft.Maui.Media.MediaPicker for attaching photos for upload.
* `TakePhotoCommand` (`ICommand`)&mdash;Defines the command that opens the camera for attaching a photo.

>tip You need to grand permissions to access the device camera and device external storage.

## Commands Related to Attachments

* `AttachFilesCommand` (`ICommand`)&mdash;Defines the command that is executed when the files the end-user picked need to be attached/uploaded.
* `DownloadAttachmentsCommand` (`ICommand`)&mdash;Defines the command that is executed when the end user initiates download of attachments for a `Telerik.Maui.Controls.Chat.ChatAttachmentsMessage`. The command parameter of this command is of type `Telerik.Maui.Controls.Chat.ChatDownloadAttachmentsCommandContext.`
* `ShareAttachmentsCommand` (`ICommand`)&mdash;Defines the command that triggers the share attachments operation.
* `RemoveAttachedFileCommand` (`ICommand`)&mdash;Defines the command that should remove an attached file from the `Telerik.Maui.Controls.RadChat.AttachedFilesSource` collection in the view model.

## Example with SendMessageCommand

Here is an example on how to define a command in the ViewModel and bind the `SendMessageCommand` to it:

1. Add the command's `Execute` method.

<snippet id='chat-commands-executemethod' />

2. Define the `RadChat` component:

<snippet id='chat-commands-xaml' />

3. Add the ViewModel:

<snippet id='chat-commands-viewmodel' />

## Example with AttachFilesCommand

1. Define the `RadChat` component:

<snippet id='chat-attachments-xaml' />

2. Add the `ViewModel` with the `AttachFilesCommand` definition:

<snippet id='chat-with-attachments-view-model' />

3. Create a sample `MessageItem` model:

<snippet id='chat-message-item' />

4. Create `AttachmentsItem` class and define the attachments collection property:

<snippet id='chat-attachments-item' />

5. Define an `AttachmentData` class to hold the attachment information:

<snippet id='chat-attachment-data' />

6. Define the custom class for the attachments file data:

<snippet id='chat-attached-file-data' />

7. Define a converter to convert a data item to a chat attachment. In general here you need to create and set up the corresponding `Telerik.Maui.Controls.Chat.ChatAttachedFile` for the given business object: 

<snippet id='chat-attached-file-converter' />

8. Define a custom converter that converts from chat specific objects to business objects, so that the `ViewModel` does not have to handle chat specific classes:

<snippet id='chat-attached-file-command-converter' />

9. The `ItemConverter` is need in MVVM scenario as custom items are used:

<snippet id='chat-attachment-item-converter' />

10. The demo uses a custom data file server for uploading, downloading and deleting attachments:

<snippet id='chat-data-server' />

## See Also

- [MVVM Support]({% slug chat-mvvm-support%})
- [Chat Items]({%slug chat-items-overview %})
