---
title: Styling the Filtering UI with Distinct Values - DataGrid for MAUI
description: Learn how to style the Filtering UI in the DataGrid for MAUI by changing the color of the area with the checkboxes.
type: how-to
page_title: Styling the Filtering UI with Distinct Values - DataGrid for MAUI
slug: styling-filtering-ui-distinct-values-datagrid-maui
tags: maui, datagrid, filtering, styling, distinct values
res_type: kb
---
# Environment
| Version | Product | Author | 
| --- | --- | ---- | 
| 6.6.0 | DataGrid for MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

# Description

I want to style the filtering UI in the DataGrid for MAUI by changing the color of the area with the distinct values.

# Solution

To style the distinct values area in the filtering UI, you can use an implicit style and customize the colors in the template. Here are the steps to achieve this:

1. Define an implicit style for the `DataGridDistinctValuesFilterView` type:

```xaml
<Style TargetType="telerik:DataGridDistinctValuesFilterView">
    <Setter Property="BackgroundColor" Value="Red"/>
    <Setter Property="ControlTemplate" Value="{StaticResource DataGridDistinctValuesFilterView_ControlTemplate}"/>
</Style>
```

2. Customize the colors in the `DataGridDistinctValuesFilterView_ControlTemplate` template:

```xaml
            <DataTemplate x:Key="DistinctValue_ItemTemplate">
                <Grid>
                    <HorizontalStackLayout telerikControls:RadCheckBox.ToggleOnTap="{Binding Source={x:Reference checkBox}}"
                            Margin="5">
                        <telerikControls:RadCheckBox x:Name="checkBox"
                                  IsChecked="{Binding IsSelected, Mode=TwoWay}" />
                        <Label Text="{Binding Text}"
                Margin="8, 0, 0, 0" />
                    </HorizontalStackLayout>
                </Grid>
            </DataTemplate>

            <ControlTemplate x:Key="DataGridDistinctValuesFilterView_ControlTemplate">
                <Grid RowDefinitions="Auto, Auto"
       RowSpacing="7">
                    <HorizontalStackLayout telerikControls:RadCheckBox.ToggleOnTap="{Binding Source={x:Reference checkBox}}">
                        <telerikControls:RadCheckBox x:Name="checkBox"
                                          IsChecked="{TemplateBinding SelectAll, Mode=TwoWay}" />
                        <Label Text="SelectAll"
                FontAttributes="Bold"
                Margin="8, 0, 0, 0" />
                    </HorizontalStackLayout>
                    <Grid Grid.Row="1"
           IsClippedToBounds="True">
                        <Frame
                BackgroundColor="White" />
                        <telerikControls:RadItemsControl ItemsSource="{TemplateBinding DistinctValues}" x:Name="itemsControl"
                                              ItemTemplate="{StaticResource DistinctValue_ItemTemplate}" BackgroundColor="LightBlue"
                                              MinimumHeightRequest="{TemplateBinding DistinctValuesMinimumHeight}"
                                              MaximumHeightRequest="{TemplateBinding DistinctValuesMaximumHeight}"
                                              Margin="6, 3" />
                    </Grid>
                </Grid>
            </ControlTemplate>
```

3. Define the DataGrid control:

```xaml
<telerik:RadDataGrid x:Name="datagrid" AutoGenerateColumns="False">
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridTextColumn PropertyName="Country" >
        </telerik:DataGridTextColumn>
        <telerik:DataGridTextColumn PropertyName="Capital"/>
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

