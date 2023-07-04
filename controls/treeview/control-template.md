---
title: Control Template
page_title: .NET MAUI TreeView Documentation - Control Template
description: Review what is the default control template of the Telerik .NET MAUI TreeView control and all elements we have in the template. 
position: 7
slug: treeview-control-template
---

# .NET MAUI TreeView Control Template

The Telerik .NET MAUI TreeView control has a set of elements inside the `ControlTemplate`. These elements are `CheckBox`, `Image`, `Expand/Collapse` indicator and the `Label`. 

If you want to fully customize the appearance of these elements you have to use the `ControlTemplate`. 

Here is an example how to use the `ControlTemplate`. 

**1.** Define the `RadTreeView` control and the `ControlTemplate`: 

```XAML
    <ContentPage.Resources>
        <ResourceDictionary>
            <!-- default control template with modifications for adding a button at the end -->
            <ControlTemplate x:Key="myTemplate">
                <telerik:RadBorder BackgroundColor="LightBlue"
                                       BorderColor="{TemplateBinding BorderColor}"
                                       BorderBrush="{TemplateBinding BorderBrush}"
                                       BorderThickness="{TemplateBinding BorderThickness}"
                                       CornerRadius="{TemplateBinding CornerRadius}"
                                       Padding="{TemplateBinding ContentPadding}">
                    <telerik:TreeViewItemLayout Indentation="{TemplateBinding Indentation}"
                                                Spacing="{TemplateBinding Spacing}">

                        <telerik:TreeViewItemExpandButton Style="{TemplateBinding ExpandButtonStyle}"
                                                              Command="{TemplateBinding ToggleExpandedCommand}"
                                                              TextColor="{TemplateBinding TextColor}"
                                                              IsExpanded="{TemplateBinding IsExpanded}"
                                                              IsLeaf="{TemplateBinding IsLeaf}"
                                                              IsEnabled="{TemplateBinding IsEnabled}"
                                                              IsVisible="{TemplateBinding IsExpandButtonVisible}" />
                        <telerik:TreeViewItemCheckBox Style="{TemplateBinding CheckBoxStyle}"
                                                          IsChecked="{TemplateBinding IsChecked}"
                                                          IsEnabled="{TemplateBinding IsEnabled}"
                                                          IsVisible="{TemplateBinding IsCheckBoxVisible}" />
                     
                        <telerik:TreeViewItemImage Source="{TemplateBinding ImageSource}"
                                                       Style="{TemplateBinding ImageStyle}"
                                                       IsEnabled="{TemplateBinding IsEnabled}"
                                                       IsVisible="{TemplateBinding IsImageVisible}" />
                            <!-- content presenter for presenting the (ItemTemplate/Text if itemtemplate is not used) -->
                        <ContentPresenter/>

                            <!-- added additional button at the end of the control template -->
                        <telerik:TreeViewItemButton Text="MyButton" WidthRequest="100" BackgroundColor="Red" HorizontalOptions="End"/>
                    </telerik:TreeViewItemLayout>
                </telerik:RadBorder>
            </ControlTemplate>
            
            <Style TargetType="telerik:TreeViewItemView" x:Key="myStyle" >
                <!-- control template can be defined through style -->
                <Setter Property="ControlTemplate" Value="{StaticResource myTemplate}"/>
                <Setter Property="IsImageVisible" Value="True"/>
            </Style>
            
        </ResourceDictionary>
    </ContentPage.Resources>
    <telerik:RadTreeView x:Name="treeView"
                         ItemStyle="{StaticResource myStyle}"
                         ItemsSource="{Binding Items}">
        <telerik:TreeViewDescriptor ItemsSourcePath="Children"
                                DisplayMemberPath="Name"
                                TargetType="{x:Type local:Item}" />
    </telerik:RadTreeView>
```

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `Item` class:

<snippet id='treeview-getting-started-item' />

**4.** Add the `ViewModel` class:

<snippet id='treeview-getting-started-viewmodel' />

## See Also

* [Expand and Collapse TreeView Items]({%slug treeview-expand-collapse%})
* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})
