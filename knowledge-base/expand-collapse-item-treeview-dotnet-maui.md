---
title: Using Expand and Collapse Commands in TreeView for .NET MAUI
description: Learn how to use the Expand and Collapse commands in the TreeView control for .NET MAUI.
type: how-to
page_title: How to Expand and Collapse Items in TreeView for .NET MAUI
meta_title: How to Expand and Collapse Items in TreeView for .NET MAUI
slug: expand-collapse-item-treeview-dotnet-maui
tags: treeview, .net maui, expand, collapse, commands, xaml, converter, viewmodel
res_type: kb
---

## Environment

| Version | Control | Author |
| ---- | ---- |  ---- |
| 12.0.0 | Telerik UI for .NET MAUI TreeView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to expand and collapse items in the [TreeView](https://www.telerik.com/maui-ui/documentation/controls/treeview/overview) control for .NET MAUI using commands. The commands should take a path as a parameter, entered in an Entry control, and convert it into an item path using a converter.

This knowledge base article also answers the following questions:
- How can I expand a specific item in the TreeView control for .NET MAUI?
- How can I collapse a specific item in the TreeView control for .NET MAUI?
- How to use a path converter with the TreeView commands for .NET MAUI?

## Solution

To expand and collapse items in the TreeView control for .NET MAUI, follow these steps:

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

3. Implement a converter to transform the text entered in the Entry into an item path:

    ```c#
    public class StringPathConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
        {
            if (value is string path)
            {
                return path.Split('/', '\\', StringSplitOptions.RemoveEmptyEntries);
            }

            return null;
        }

        public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
        {
            if (value is IEnumerable path)
            {
                var items = path.OfType<object>();

                return string.Join("/", items);
            }

            return null;
        }
    }
    ```

4. Define the TreeView in XAML with the converter, Entry for path input, and buttons for expand/collapse commands:

    ```xml
    <ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
                 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                 xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
                 xmlns:local="clr-namespace:MauiApp14"
                 x:Class="MauiApp14.MainPage">
        <ContentPage.Resources>
            <ResourceDictionary>
                <local:StringPathConverter x:Key="StringPathConverter" />
            </ResourceDictionary>
        </ContentPage.Resources>
        <Grid RowDefinitions="Auto, *"
              RowSpacing="5">
            <VerticalStackLayout Grid.Row="0"
                                 Spacing="5">
                <Grid ColumnDefinitions="Auto, *"
                      ColumnSpacing="5">
                    <Label Grid.Column="0"
                           Text="Path"
                           VerticalOptions="Center" />
                    <Entry x:Name="pathEntry"
                           Grid.Column="1"
                           Placeholder="Example: Folder 1/Folder 10" />
                </Grid>
                <HorizontalStackLayout Spacing="5">
                    <Button Text="Expand using command"
                            Command="{Binding ExpandCommand, Source={x:Reference treeView}}"
                            CommandParameter="{Binding Text, Source={x:Reference pathEntry}, Converter={StaticResource StringPathConverter}}" />
                    <Button Text="Collapse using command"
                            Command="{Binding CollapseCommand, Source={x:Reference treeView}}"
                            CommandParameter="{Binding Text, Source={x:Reference pathEntry}, Converter={StaticResource StringPathConverter}}" />
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
    </ContentPage>
    ```

## See Also

- [TreeView Overview Documentation](https://www.telerik.com/maui-ui/documentation/controls/treeview/overview)
- [TreeView Expand/Collapse Items](https://www.telerik.com/maui-ui/documentation/controls/treeview/expand-collapse)