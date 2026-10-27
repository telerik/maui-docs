---
title: Events
meta_title: .NET MAUI {{ControlName}} Documentation - Events
description: Learn how to handle the {{EventName1}} and {{EventName2}} events of the Telerik UI for .NET MAUI {{ControlName}} to respond to user actions.
position: {{events-position}}
slug: {{control-slug}}-events
---

# .NET MAUI {{ControlName}} Events

The Telerik UI for .NET MAUI {{ControlName}} control exposes a set of events that users trigger through interaction. Handle these events to respond to user actions and customize the behavior of the control.

The {{ControlName}} exposes the [`{{EventName1}}`](#{{event1-anchor}}) and [`{{EventName2}}`](#{{event2-anchor}}) events.

## {{EventName1}}

The {{ControlName}} raises the `{{EventName1}}` event when {{condition}}. The `{{EventName1}}` event handler receives the following parameters:

* The `sender` argument, which is of type `object`, but can be cast to the `{{RadClassName}}` type.
* A `{{EventArgsType}}` object, which provides {{description}}.

The following example demonstrates how to handle the `{{EventName1}}` event:

1. Define the {{ControlName}}:

    <snippet id='{{control-slug}}-{{event1-slug}}-xaml' />

1. Define the event handler:

    <snippet id='{{control-slug}}-{{event1-slug}}' />

## {{EventName2}}

The {{ControlName}} raises the `{{EventName2}}` event when {{condition}}. The `{{EventName2}}` event handler receives the following parameters:

* The `sender` argument, which is the `{{RadClassName}}` control.
* A `{{EventArgsType}}` object, which provides the following properties:
    * `PropertyName`&mdash;{{Description.}}
    * `PropertyName`&mdash;{{Description.}}

The following example demonstrates how to handle the `{{EventName2}}` event:

1. Define the {{ControlName}}:

    <snippet id='{{control-slug}}-{{event2-slug}}-xaml' />

1. Define the event handler:

    <snippet id='{{control-slug}}-{{event2-slug}}' />

## See Also

- [{{ControlName}} Commands]({% slug {{control-slug}}-commands %})
- [Styling the {{ControlName}}]({% slug {{control-slug}}-styling %})
