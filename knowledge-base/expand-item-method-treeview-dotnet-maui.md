---
title: Using the Expand Method of TreeView in UI for .NET MAUI
description: Learn how to use the Expand method of the TreeView control in UI for .NET MAUI to expand specific nodes programmatically.
type: how-to
page_title: How to Expand Nodes in TreeView for UI for .NET MAUI
meta_title: How to Expand Nodes in TreeView for UI for .NET MAUI
slug: expand-item-method-treeview-dotnet-maui
tags: treeview, ui-for-dotnet-maui, expand-method, control, method
res_type: kb
---

## Environment

Version| Control | Author |
| ---- | ---- |  ---- |
| 12.0.0 | Telerik UI for .NET MAUI TreeView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to use the `Expand` method of the [TreeView](https://www.telerik.com/maui-ui/documentation/controls/treeview/overview) for UI for .NET MAUI to programmatically expand specific nodes based on their identity and hierarchy.

This knowledge base article also answers the following questions:
- How to programmatically expand nodes in TreeView for UI for .NET MAUI?
- How to call `Expand` method in TreeView for UI for .NET MAUI?
- How to expand specific nodes in TreeView using code?

## Solution

To expand specific nodes in the TreeView control, follow these steps:

1. Define a data model for the TreeView items:

    ```c#
    public class FileSystemNode : NotifyPropertyChangedBase
    {
        private FolderNode parent;
        private string name;

        public FolderNode Parent
        {
            get => this.parent;
            set => this.UpdateValue(ref this.parent, value);
        }

        public string Name
        {
            get => this.name;
            set => this.UpdateValue(ref this.name, value);
        }

        public override string ToString()
        {
            return this.name;
        }
    }

    public class FolderNode : FileSystemNode
    {
        public FolderNode()
        {
            this.Children = new ObservableCollection<FileSystemNode>();
        }

        public IList<FileSystemNode> Children { get; }
    }

    public class FileNode : FileSystemNode
    {
    }
    ```

2. Create a `ViewModel` to manage your data and commands:

    ```c#
    public class FileSystemViewModel : NotifyPropertyChangedBase
    {
        private const int parentCount = 10;
        private const int childCount = 10;
        private const int fileCount = 10;

        private readonly ObservableCollection<FileSystemNode> fileSystemNodes;
        private FileSystemNode selectedNode;
        private int folderIndex;
        private int fileIndex;

        public FileSystemViewModel()
        {
            this.fileSystemNodes = new ObservableCollection<FileSystemNode>();
            this.InitializeFileSystem();

            Data = CreateData(200);
        }
        public List<int> Data { get; set; }

        internal static List<int> CreateData(int count)
        {
            List<int> source = new List<int>();

            for (int i = 0; i < count; i++)
            {
                source.Add(i);
            }

            return source;
        }
        public FileSystemNode SelectedNode
        {
            get => this.selectedNode;
            set => this.UpdateValue(ref this.selectedNode, value);
        }

        public IList<FileSystemNode> FileSystemNodes => this.fileSystemNodes;

        private void InitializeFileSystem()
        {
            for (int parentIndex = 0; parentIndex < parentCount; parentIndex++)
            {
                var parentFolderNode = this.CreateFolderNode();

                for (int childIndex = 0; childIndex < childCount; childIndex++)
                {
                    var childFolderNode = this.CreateFolderNode();

                    for (int fileIndex = 0; fileIndex < fileCount; fileIndex++)
                    {
                        var childFileNode = this.CreateFileNode();

                        childFileNode.Parent = childFolderNode;
                        childFolderNode.Children.Add(childFileNode);
                    }

                    childFolderNode.Parent = parentFolderNode;
                    parentFolderNode.Children.Add(childFolderNode);
                }

                this.fileSystemNodes.Add(parentFolderNode);
            }
        }

        private FolderNode CreateFolderNode()
        {
            this.folderIndex++;

            return new FolderNode
            {
                Name = $"Folder {this.folderIndex}"
            };
        }

        private FileNode CreateFileNode()
        {
            this.fileIndex++;

            return new FileNode
            {
                Name = $"File {this.fileIndex}"
            };
        }
    }
    ```



4. Define the TreeView in XAML with the button for calling the `Expand()` method::

    ```xml
    <Grid RowDefinitions="Auto, *" RowSpacing="5">
        <VerticalStackLayout Grid.Row="0" Spacing="5">
            <HorizontalStackLayout Spacing="5">
                <Button Text="Expand Folder 1 / Folder 2 using Expand method"
                        Clicked="OnExpandClicked" />
            </HorizontalStackLayout>
        </VerticalStackLayout>
        <telerik:RadTreeView x:Name="treeView"
                             Grid.Row="1"
                             ItemsSource="{Binding FileSystemNodes}"
                             SelectedItem="{Binding SelectedNode, Mode=TwoWay}">
            <telerik:TreeViewDescriptor TargetType="{x:Type local:FolderNode}"
                                        IdentityMemberPath="Name"
                                        DisplayMemberPath="Name"
                                        ItemsSourcePath="Children" />
            <telerik:TreeViewDescriptor TargetType="{x:Type local:FileNode}"
                                        IdentityMemberPath="Name"
                                        DisplayMemberPath="Name" />
        </telerik:RadTreeView>
    </Grid>
    ```

5. Define the `OnExpandClicked` method in the code-behind and call the `RadTreeView.Expand()` method. In the method pass the item path of the nodes to expand.

    ```csharp
    private void OnExpandClicked(object sender, EventArgs e)
    {
        if (this.BindingContext is not FileSystemViewModel vm)
        {
            return;
        }

        // Find the parent node named "Folder 1" and its child node "Folder 2"
        var parent = vm.FileSystemNodes
            .OfType<FolderNode>()
            .FirstOrDefault(p => p.Name == "Folder 1");

        var child = parent?
            .Children
            .OfType<FolderNode>()
            .FirstOrDefault(c => c.Name == "Folder 2");

        if (parent is not null && child is not null)
        {
            var itemPath = new object[] { parent.Name, child.Name };
            this.treeView.Expand(itemPath); // Expand the node using the item path
        }
    }
    ```

## See Also

- [TreeView Overview Documentation](https://www.telerik.com/maui-ui/documentation/controls/treeview/overview)
- [TreeView Expand/Collapse Items](https://www.telerik.com/maui-ui/documentation/controls/treeview/expand-collapse)