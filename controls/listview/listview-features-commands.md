---
title: Commands
page_title: .NET MAUI ListView Documentation | Commands
description: Check our &quot;Commands&quot; documentation article for Telerik ListView for .NET MAUI control.
position: 13
slug: listview-features-commands
description: Describing the commands of the RadListView
tags: commands
---

# Commands

The Command design-pattern is widely used in the XAML and MVVM world. RadListView strictly follows the Command design-pattern best practices and provides an intuitive and easy-to-use set of APIs that allow you to control various aspects of RadListView’s behavior.

RadListView exposes a **Commands** collection that allows you to register custom commands with each control’s instance through the RadListView.Commands property:

* Commands: Gets the collection with all the custom commands registered with the CommandService. Custom commands have higher priority than the built-in (default) ones.

## CommandId Enumeration

All predefined commands within a RadListView instance are identified by a member of the CommandId enumeration. This member is actually the key that relates a command instance to a particular action/routine within the owning ListView.

To register a custom command within a RadListView instance you can:

* [Inherit from the ListViewCommand class](#inheriting-from-listviewcommand) and override its CanExecute and Execute methods.
* [Use the ListViewUserCommand class and bind its Command property](#binding-listviewusercommand) to a Command in your ViewModel.

In both cases, you need to set the Id property of the new command so that it can be properly associated with the desired action/event.

Following are the members of the **CommandId** enumerations:

* **ItemTap**
* **ItemSwiping**
* **ItemSwipeCompleted**
* **ItemSwipeStarting**
* **PullToRefreshRequested**
* **SelectionChanged**
* **LoadOnDemand**
* **ItemHold**
* **GroupHeaderTap**
* **ReorderStarting**
* **ReorderEnded**

>tip These actions correspond to the events exposed by RadListView. For more details, see the [Events]({%slug listview-features-events%}) topic.

For each of the available commands, there is a *context* object of type [CommandId]CommandContext, for example, ItemTapCommandContext, ItemHoldCommandContext, etc. The *context* object is passed as a parameter in its Execute method and provides information identical to the corresponding event's args.

## Inheriting from ListViewCommand

To demonstrate inheriting from ListViewCommand, the following example handles the **ItemTap** action as a Command:

**1.** Create a class that inherits from ListViewCommand and set its Id property. Then override the **CanExecute** and **Execute** methods:

<snippet id='listview-features-commands-listviewcommand'/>
```C#
public class ItemTappedUserCommand : ListViewCommand
{
	public ItemTappedUserCommand()
	{
		Id = CommandId.ItemTap;
	}
	public override bool CanExecute(object parameter)
	{
		return true;
	}
	public override void Execute(object parameter)
	{
		var tappedItem = (parameter as ItemTapCommandContext).Item;
		//add your logic here
		Application.Current.MainPage.DisplayAlert("", "You've selected " + tappedItem, "OK");
	}
}
```

**2.** Add the custom command to the Commands collection of the RadListView instance:

<snippet id='listview-features-commands-add'/>
```C#
listView.Commands.Add(new ItemTappedUserCommand());
```

## Binding ListViewUserCommand

With the ListViewUserCommand binding approach, you can directly handle the custom commands in the ViewModel. Here is a quick example:

**1.** Add the custom command to the ViewModel:

<snippet id='listview-features-commands-viewmodel'/>
```C#
public class ViewModel
{
	public ViewModel()
	{
		this.Source = new List<string> { "Tom", "Anna", "Peter", "Teodor", "Martin" };
		this.ItemTapCommand = new Command<ItemTapCommandContext>(this.ItemTapped);
	}
	private void ItemTapped(ItemTapCommandContext context)
	{
		var tappedItem = context.Item;
		//add your logic here
		Application.Current.MainPage.DisplayAlert("", "You've selected " + tappedItem, "OK");
	}
	public List<string> Source { get; set; }
	public ICommand ItemTapCommand { get; set; }
}
```

**2.** Bind the ItemTapCommand through the predefined ListViewUserCommand command. Its Id property is used to map the command to the corresponding action with the control:

```XAML
<telerikDataControls:RadListView x:Name="listView" 
								 ItemsSource="{Binding Source}">
	<telerikDataControls:RadListView.BindingContext>
		<local:ViewModel />
	</telerikDataControls:RadListView.BindingContext>
	<telerikDataControls:RadListView.Commands>
		<telerikListViewCommands:ListViewUserCommand Id="ItemTap" 
													 Command="{Binding ItemTapCommand}" />
	</telerikDataControls:RadListView.Commands>
</telerikDataControls:RadListView>
```

**3.** Define the telerikListViewCommands:

```XAML
xmlns:telerikListViewCommands="clr-namespace:Telerik.XamarinForms.DataControls.ListView.Commands;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Events]({%slug listview-features-events%})
- [Selection]({%slug listview-features-selection%})
- [Reordering]({%slug listview-features-reorder-items%})


