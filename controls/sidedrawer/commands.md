---
title: Commands
page_title: .NET MAUI SideDrawer Documentation | Commands
description: Check our &quot;Commands&quot; documentation article for Telerik SideDrawer for .NET MAUI control.
position: 5
slug: sidedrawer-features-commands
---

# Overview

The SideDrawer control exposes a `Commands` collection that allows you to
register custom commands with each control’s instance. The commands allow the user to easily change and extend the control default behavior.

Each element in the `Commands` collection inherits from the `SideDrawerCommandBase` class, and can override the `CanExecute()` and `Execute()` methods. Each command is associated with a certain event, which is represented by the command `Id` property. The property needs to be set to one of the values listed below, otherwise the command service of the control will not execute the command.

* `Opening`&mdash;Executed when the side drawer is being visualized on the device screen.
* `Opened`&mdash;Executed when the side drawer is already visualized on the device screen.
- `Closing`&mdash;Executed when the side drawer is being hidden.
- `Closed`&mdash;Executed when the side drawer is already closed.

For your convenience we have created a special `SideDrawerUserCommand` class that also exposes a `Command` dependency property which can be set to an instance of type that implements the `ICommand` interface.

# Examples

The following examples demonstrates how to use the SideDrawer commands in different scenarios.

## Inheriting from the SideDrawerCommandBase class

You can create a class deriving from the `SideDrawerCommandBase` class and set its `Id` property to the desired command trigger event. Furthermore, you can override its `CanExecute()` and `Execute()` methods. A sample implementation is shown below:

 ```C#
public class CustomDrawerCommand : SideDrawerCommandBase
{
    public CustomDrawerCommand()
    {
        this.Id = SideDrawerCommandId.Closed;
    }

    public override bool CanExecute(object parameter)
    {
        return true;
    }

    public override void Execute(object parameter)
    {
		// implement your custom logic here
    }
}
 ```

Once such command is created it can be used in XAML like this:

 ```XAML
<telerik:RadSideDrawer>
  <telerik:RadSideDrawer.Commands>
    <local:CustomDrawerCommand/>
  </telerik:RadSideDrawer.Commands>
  <telerik:RadSideDrawer.MainContent>
     <Label Text="Main content" />
  </telerik:RadSideDrawer.MainContent>
  <telerik:RadSideDrawer.DrawerContent>
 	<Label Text="Drawer content" />
  </telerik:RadSideDrawer.DrawerContent>
</telerik:RadSideDrawer>
 ```

You will need to add the following namespaces

 ```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
 ```

Where the `local` alias points to the namespace where the `CustomUserCommand` is defined.

## Using the SideDrawerUserCommand class

You can define a class that implements the `ICommand` interface:

 <snippet id='sidedrawer-customcommands-cs' />

After that you can use this class with the `SideDrawerUserCommand` in XAML like this:

 <snippet id='sidedrawer-commands-xaml' />

You will need to add the following namespaces

 ```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
 ```

and the `local` alias points to the namespace where the `CustomCommand` is defined.

## Binding to a ViewModel

Use the `SideDrawerUserCommand` to bind its `Command` property to a view model.

1. Define the ViewModel:

 <snippet id='sidedrawer-commandsviewmodel-cs' />

1. Define the CustomCommand:

 <snippet id='sidedrawer-customcommands-cs' />

1. Define the SideDrawer control:

 <snippet id='sidedrawer-commandsviewmodel-xaml' />

1. Add the following namespace:

 ```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
 ```

and the `local` alias points to the namespace where the `CustomCommand` and `ViewModel` are defined.

## See Also

- [Getting-Started]({%slug sidedrawer-getting-started%})
- [Configuration]({%slug sidedrawer-features-configuration%})
- [Transitions]({%slug sidedrawer-features-transitions%})
- [Events]({%slug sidedrawer-features-events%})