---
title: Events
page_title: .NET MAUI Conversational UI Documentation - Events
description: Learn what are the events exposed by the Telerik UI for .NET MAUI Chat
position: 7
slug: chat-events
---

# .NET MAUI Chat Events

The Telerik UI for .NET MAUI Chat allows you to attach events that will be raised when certain actions occur.

Here is a list of the available events:

* `SendMessage`&mdash;Raised when a message is sent from the chat by the current author (by clicking the send message button or pressing Enter).
* `AttachFiles`&mdash;Raised when the end user picks files to attach.
	* The `sender` argument, which is of type `object`, but can be cast to the `RadChat` type.
	* A `ChatAttachFilesEventArgs` object which provides the list of files (`IList<IFileInfo> FilesToAttach`) to attach to the chat message.

* `RemoveAttachedFile`&mdash;Raised when the end user removes an attached file, via the `X` button of the `ChatInputAreaAttachedFileItemView`.
	* The `sender` argument, which is of type `object`, but can be cast to the `RadChat` type.
	* * A `ChatRemoveAttachedFileEventArgs` object which provides the index (`Index` of type `int`) of the item that should be removed from the `Telerik.Maui.Controls.RadChat.AttachedFilesSource` and `Telerik.Maui.Controls.RadChat.AttachedFiles`.

## See Also

- [MVVM Support]({% slug chat-mvvm-support%})
- [Chat Items]({%slug chat-items-overview %})
