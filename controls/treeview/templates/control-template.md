---
title: Control Template
page_title: .NET MAUI TreeView Documentation - Control Template
description: Review what is the control template for Telerik UI for .NET MAUI TreeView control and how to modify the elements in the template.
position: 4
previous_url: /controls/treeview/control-template
slug: treeview-control-template
---

# .NET MAUI TreeView Control Template

The Telerik UI for .NET MAUI TreeView provides a `ControlTemplate` property, which defines the visual appearance of the control. To customize the looks of the TreeView, use the default template and modify it. 

The control has a set of elements inside the `ControlTemplate`. These elements are `CheckBox`, `Image`, `Expand/Collapse` indicator, and `Label`. To customize the appearance of these elements, use the `ControlTemplate`.


The following example shows how to use the `ControlTemplate` and change the appearance of the control. 

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
