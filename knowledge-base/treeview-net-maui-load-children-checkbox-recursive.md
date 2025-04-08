---
title: Handling TreeView Load Children on Demand with Recursive CheckBox Mode
description: Learn how to ensure child nodes are checked when expanding a parent node with CheckBox Mode set to Recursive in TreeView for .NET MAUI.
type: how-to
page_title: Ensuring Child Nodes are Checked in TreeView for .NET MAUI
slug: treeview-net-maui-load-children-checkbox-recursive
tags: treeview, .net maui, load children on demand, checkbox, recursive
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI TreeView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When using the [TreeView for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/treeview/overview) with `CheckBoxMode` set to `Recursive` and `LoadChildrenOnDemand` enabled, how to ensure that expanding a checked parent node automatically checks its child nodes? 

This knowledge base article also answers the following questions:
- How to add child nodes to the `CheckedItems` collection in TreeView for .NET MAUI?
- How to work with `Recursive` CheckBox Mode in TreeView for .NET MAUI?
- How to ensure child nodes are checked upon loading on demand in TreeView for .NET MAUI?

## Solution

To achieve the desired behavior, the developer has to manually add the child items of the checked parent node when loading children on demand.

**1.** Define the TreeView in XAML, enabling `LoadChildrenOnDemand` and setting the `CheckBoxMode` to `Recursive`:

```xaml
<telerik:RadTreeView x:Name="treeView"
                     ItemsSource="{Binding TreeNodes}"
                     CheckedItems="{Binding CheckedTreeNodes}"
                     CheckBoxMode="Recursive"
                     LoadChildrenOnDemandCommand="{Binding LoadChildrenOnDemandCommand}"
                     IsLoadChildrenOnDemandEnabled="True">
    <telerik:RadTreeView.ItemStyle>
        <Style TargetType="telerik:TreeViewItemView" x:DataType="local:TreeNode">
            <Setter Property="IsChecked" Value="{Binding IsChecked}" />
        </Style>
    </telerik:RadTreeView.ItemStyle>
    <telerik:TreeViewDescriptor TargetType="{x:Type local:TreeNode}"
                                DisplayMemberPath="Name"
                                ItemsSourcePath="Children" />
</telerik:RadTreeView>
```

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Implement a `TreeNode` model with an `IsChecked` property that binds to the TreeView CheckBox `IsChecked` property:

```c#
public class TreeNode : Telerik.Maui.Controls.NotifyPropertyChangedBase
{
	private ObservableCollection<TreeNode> children = new ObservableCollection<TreeNode>();
	private TreeNode parent;
	private string name;
	private bool? isChecked;

	public IList<TreeNode> Children => this.children;

	public TreeNode Parent
	{
		get => this.parent;
		set => this.UpdateValue(ref this.parent, value);
	}

	public string Name
	{
		get => this.name;
		set => this.UpdateValue(ref this.name, value);
	}

	public bool? IsChecked
	{
		get => this.isChecked;
		set => this.UpdateValue(ref this.isChecked, value);
	}
}
```

**4.** In the `ViewModel`, implement logic to add child items to the `CheckedItems` collection if the parent is checked when the children are loaded on demand:

```c#
public class LoadChildrenOnDemandViewModel : Telerik.Maui.Controls.NotifyPropertyChangedBase
{
	private const int nodesCount = 10;
	private const int loadDelay = 2000;
	private ObservableCollection<TreeNode> treeNodes = new ObservableCollection<TreeNode>();
	private ObservableCollection<TreeNode> checkedTreeNodes = new ObservableCollection<TreeNode>();
	private Command loadChildrenOnDemandCommand;
	private int nodeIndex;

	public LoadChildrenOnDemandViewModel()
	{
		this.treeNodes = new ObservableCollection<TreeNode>();
		this.checkedTreeNodes = new ObservableCollection<TreeNode>();
		this.loadChildrenOnDemandCommand = new Command<Telerik.Maui.Controls.TreeView.TreeViewLoadChildrenOnDemandCommandContext>(LoadOnDemand);
		InitializeRootNodes();
	}

	public ObservableCollection<TreeNode> TreeNodes => this.treeNodes;
	public ObservableCollection<TreeNode> CheckedTreeNodes => this.checkedTreeNodes;
	public ICommand LoadChildrenOnDemandCommand => this.loadChildrenOnDemandCommand;

	private void InitializeRootNodes()
	{
		for (int itemIndex = 0; itemIndex < nodesCount; itemIndex++)
		{
			var node = this.CreateTreeNode();
			this.treeNodes.Add(node);
		}
	}

	private async void LoadOnDemand(Telerik.Maui.Controls.TreeView.TreeViewLoadChildrenOnDemandCommandContext commandContext)
	{
		if (commandContext.Item is TreeNode parentNode)
		{
			await Task.Delay(2000); // Simulate loading delay
			LoadChildNodes(parentNode);
		}
		commandContext.Finish();
	}

	private void LoadChildNodes(TreeNode parentNode)
	{
		for (int itemIndex = 0; itemIndex < nodesCount; itemIndex++)
		{
			var childNode = this.CreateTreeNode();
			childNode.Parent = parentNode;
			parentNode.Children.Add(childNode);

			if (parentNode.IsChecked == true)
			{
				this.checkedTreeNodes.Add(childNode);
			}
		}
	}

	private TreeNode CreateTreeNode()
	{
		this.nodeIndex++;

		return new TreeNode
		{
			Name = $"Node {this.nodeIndex}"
		};
	}
}
```

**5.** Set the `ViewModel` as the `BindingContext` of your page:

```csharp
this.BindingContext = new LoadChildrenOnDemandViewModel();
```

By following these steps, when a parent node is checked and then expanded, all its child nodes will be automatically added to the `CheckedItems` collection, ensuring they are checked as well.

## See Also

- [TreeView Overview](https://docs.telerik.com/devtools/maui/controls/treeview/overview)
- [CheckBox Modes in TreeView](https://docs.telerik.com/devtools/maui/controls/treeview/checkboxes)
- [Loading Children on Demand in TreeView](https://docs.telerik.com/devtools/maui/controls/treeview/load-children-on-demand)
