---
title: Customizing DataGrid Filtering UI in UI for .NET MAUI
description: Learn how to customize the filtering UI in Telerik DataGrid to remove the filtering criteria and display distinct values checkbox only.
type: how-to
page_title: Modify Filtering UI in Telerik DataGrid for Distinct Values Only
meta_title: Modify Filtering UI in Telerik DataGrid for Distinct Values Only
slug: datagrid-filtering-ui-customization-keep-only-distinct-values
tags: datagrid, ui-for-net-maui, filter, control-template, filtering-ui
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to customize the filtering UI in the Telerik [DataGrid](https://www.telerik.com/maui-ui/datagrid) in my UI for .NET MAUI application. Specifically, I need to remove the filtering criteria section and display only the distinct values checkbox along with the close and filter buttons.

This knowledge base article also answers the following questions:
- How to modify the filter control template in Telerik DataGrid?
- How to remove filtering criteria from Telerik DataGrid filtering UI?
- How to display only distinct values in DataGrid filtering UI?

## Solution

To modify the filtering UI in Telerik DataGrid, update the filtering control template. Add TelerikTheming to your project and locate the `DataGrid.xaml` file under `TelerikTheming/Styles/Platform`. Use the `DataGridTextFilterControlControlTemplate_Mobile` for mobile or `DataGridTextFilterControlControlTemplate_Desktop` for desktop.

Follow these steps:

1. Add TelerikTheming resources to your project. Refer to the [TelerikTheming documentation](https://www.telerik.com/maui-ui/documentation/styling-and-themes/overview).

2. Open the `DataGrid.xaml` file under `TelerikTheming/Styles/Platform`. Locate the control templates for filtering.

3. Use the `DataGridTextFilterControlControlTemplate_Mobile` and remove unnecessary parts. Keep only the `DataGridDistinctValuesFilterView`, the close button, and the filter/reset buttons.

4. Define the updated template in your XAML resources.

Example:

```xml
<ContentPage.Resources>
	<ResourceDictionary>
		<telerikMauiControls:AreEqualToBoolConverter x:Key="AreEqualToBoolConverter" />
		<telerikMauiControls:IsOfTypeConverter x:Key="IsColumnConverter" Type="{x:Type telerikDataGrid:DataGridColumn}" />
		<telerikMauiControls:NullOrEmptyToBoolConverter x:Key="NullOrEmptyToBoolConverter" />

		<Style x:Key="DataGridFilterControlMatchCaseButtonStyle_iOS" TargetType="telerikMauiControls:RadToggleButton">
			<Setter Property="Background" Value="{DynamicResource RadDataGridFilterControlMatchCaseButtonBackgroundColor}" />
		</Style>

		<Style x:Key="DataGridFilterControlBorderStyle_Mobile" TargetType="telerikMauiControls:RadBorder">
			<Setter Property="BackgroundColor" Value="{DynamicResource RadDataGridFilterControlBackgroundColor}" />
			<Setter Property="BorderColor" Value="{DynamicResource RadBorderAltColor}" />
			<Setter Property="BorderThickness" Value="1" />
		</Style>

		<Style x:Key="DataGridFilterControlRootBorderStyle_Mobile" TargetType="telerikMauiControls:RadBorder" BasedOn="{StaticResource DataGridFilterControlBorderStyle_Mobile}">
			<Setter Property="BorderThickness" Value="0" />
			<Setter Property="Padding" Value="{OnPlatform Default=0, iOS='0, 8'}" />
		</Style>

		<Style x:Key="DataGridFilterControlSeparatorStyle_Mobile" TargetType="telerikMauiControls:RadBorder">
			<Setter Property="BackgroundColor" Value="{DynamicResource RadBorderAltColor}" />
			<Setter Property="HeightRequest" Value="1" />
		</Style>

		<Style x:Key="DataGridFilterControlMatchCaseButtonStyle" TargetType="telerikMauiControls:RadToggleButton">
			<Setter Property="Content" Value="{x:Static telerikMauiCore:TelerikFont.IconMatchCase}" />
			<Setter Property="FontFamily" Value="{x:Static telerikMauiCore:TelerikFont.Name}" />
			<Setter Property="FontSize" Value="16" />
			<Setter Property="Padding" Value="0" />
			<Setter Property="WidthRequest" Value="{OnPlatform Default=44, iOS=36, MacCatalyst=30, WinUI=32}" />
			<Setter Property="HeightRequest" Value="{OnPlatform Default=44, iOS=36, MacCatalyst=30, WinUI=32}" />
		</Style>

		<Style x:Key="DataGridTextOnlyButtonStyle" TargetType="telerikMauiControls:RadButton">
			<Setter Property="FontSize" Value="14" />
			<Setter Property="TextColor" Value="{DynamicResource RadPrimaryColor}" />
			<Setter Property="BackgroundColor" Value="Transparent" />
			<Setter Property="BorderWidth" Value="0" />
			<Setter Property="VisualStateManager.VisualStateGroups">
				<VisualStateGroupList>
					<VisualStateGroup Name="CommonStates">
						<VisualState Name="Normal" />
						<VisualState Name="PointerOver">
							<VisualState.Setters>
								<Setter Property="telerikMauiControls:RadButton.BackgroundColor" Value="{DynamicResource RadDataGridCloseButtonPointerOverBackgroundColor}" />
							</VisualState.Setters>
						</VisualState>
						<VisualState Name="Disabled">
							<VisualState.Setters>
								<Setter Property="telerikMauiControls:RadButton.TextColor" Value="{DynamicResource LabelDisabledTextColor}" />
							</VisualState.Setters>
						</VisualState>
					</VisualStateGroup>
				</VisualStateGroupList>
			</Setter>
		</Style>

		<Style x:Key="DataGridCloseButtonStyle" TargetType="telerikMauiControls:RadButton" BasedOn="{StaticResource DataGridTextOnlyButtonStyle}">
			<Setter Property="FontFamily" Value="Arial" />
			<Setter Property="FontAttributes" Value="{OnPlatform Default=None, Android=Bold, iOS=Bold}" />
			<Setter Property="Text" Value="&#x2715;" />
			<Setter Property="TextColor" Value="{DynamicResource RadSubtleColor}" />
			<Setter Property="Padding" Value="0" />
			<Setter Property="WidthRequest" Value="{OnPlatform Default=40, MacCatalyst=20, WinUI=22}" />
			<Setter Property="HeightRequest" Value="{OnPlatform Default=40, MacCatalyst=20, WinUI=22}" />
		</Style>

		<Style x:Key="DataGridFilterControlApplyFilterButtonStyle_Mobile" TargetType="telerikMauiControls:RadButton" BasedOn="{StaticResource DataGridTextOnlyButtonStyle}">
			<Setter Property="TextTransform" Value="{OnPlatform Default=None, Android=Uppercase}" />
			<Setter Property="Padding" Value="{OnPlatform Default='30, 8', iOS='24, 12'}" />
		</Style>

		<Style x:Key="DataGridFilterControlApplyFilterButtonStyle" TargetType="telerikMauiControls:RadButton" BasedOn="{StaticResource DataGridFilterControlApplyFilterButtonStyle_Mobile}" />

		<Style x:Key="DataGridFilterControlResetFilterButtonStyle" TargetType="telerikMauiControls:RadButton" BasedOn="{StaticResource DataGridTextOnlyButtonStyle}">
			<Setter Property="TextTransform" Value="{OnPlatform Default=None, Android=Uppercase}" />
			<Setter Property="Padding" Value="{OnPlatform Default='30, 8', iOS='24, 12'}" />
		</Style>

		<ControlTemplate x:Key="DataGridTextFilterControlControlTemplate_Mobile">
			<telerikMauiControls:RadBorder Style="{StaticResource DataGridFilterControlRootBorderStyle_Mobile}">
				<Grid RowDefinitions="*, Auto, Auto">
					<ScrollView>
						<VerticalStackLayout>
							<telerikDataGrid:DataGridDistinctValuesFilterView DistinctValues="{TemplateBinding DistinctValues}"
                                                                      IsVisible="{TemplateBinding DistinctValues, Converter={StaticResource NullOrEmptyToBoolConverter}}"
                                                                      Margin="{OnPlatform Android='16, 12', iOS=16}" />
							<telerikMauiControls:RadBorder Style="{StaticResource DataGridFilterControlSeparatorStyle_Mobile}" />
							<!--<VerticalStackLayout Margin="{OnPlatform Android=16, iOS='16, 24'}">
								<Label Text="{telerikMauiControls:Localize DataGrid_Filter_ShowRowsWithValueThat}"
                               FontAttributes="Bold"
                               Margin="{OnPlatform Android='0, 0, 0, 12', iOS='0, 0, 0, 8'}" />
								<telerikMauiControls:RadComboBox ItemsSource="{TemplateBinding DescriptorOperators}"
                                                         SelectedItem="{TemplateBinding FirstDescriptorOperator, Mode=TwoWay}"
                                                         IsClearButtonVisible="False"
                                                         Margin="{OnPlatform Android='0, 4', iOS='0, 8'}" />
								<Grid ColumnDefinitions="*, Auto"
                              ColumnSpacing="{OnPlatform Android=8, iOS=10}"
                              Padding="{OnPlatform Android='0, 4', iOS='0, 8'}">
									<telerikMauiControls:RadEntry Text="{TemplateBinding FirstDescriptorValue, Mode=TwoWay}"
                                                          Placeholder="{telerikMauiControls:Localize DataGrid_FilterWatermarkText}" />
									<telerikMauiControls:RadToggleButton Grid.Column="1"
                                                                 IsToggled="{TemplateBinding IsFirstDescriptorCaseSensitive}"
                                                                 Style="{StaticResource DataGridFilterControlMatchCaseButtonStyle}"
                                                                 HorizontalOptions="End"
                                                                 VerticalOptions="Center" />
								</Grid>
								<telerikMauiControls:RadSegmentedControl ItemsSource="{TemplateBinding LogicalOperators}"
                                                                 SelectedIndex="{TemplateBinding LogicalOperatorIndex, Mode=TwoWay}"
                                                                 HeightRequest="{OnPlatform Android={Binding Height, Source={Reference picker}}}"
                                                                 Margin="{OnPlatform Android='0, 12'}" />
								<telerikMauiControls:RadComboBox x:Name="picker"
                                                         ItemsSource="{TemplateBinding DescriptorOperators}"
                                                         SelectedItem="{TemplateBinding SecondDescriptorOperator, Mode=TwoWay}"
                                                         IsClearButtonVisible="False"
                                                         Margin="{OnPlatform iOS='0, 8'}" />
								<Grid ColumnDefinitions="*, Auto"
                              ColumnSpacing="{OnPlatform Android=8, iOS=10}"
                              Padding="{OnPlatform Android='0, 4', iOS='0, 8'}">
									<telerikMauiControls:RadEntry Text="{TemplateBinding SecondDescriptorValue, Mode=TwoWay}"
                                                          Placeholder="{telerikMauiControls:Localize DataGrid_FilterWatermarkText}" />
									<telerikMauiControls:RadToggleButton Grid.Column="1"
                                                                 IsToggled="{TemplateBinding IsSecondDescriptorCaseSensitive}"
                                                                 Style="{StaticResource DataGridFilterControlMatchCaseButtonStyle}"
                                                                 HorizontalOptions="End"
                                                                 VerticalOptions="Center" />
								</Grid>
							</VerticalStackLayout>-->
						</VerticalStackLayout>
					</ScrollView>
					<telerikMauiControls:RadButton Command="{TemplateBinding CloseCommand}"
                                           HorizontalOptions="End"
                                           VerticalOptions="Start"
                                           Style="{StaticResource DataGridCloseButtonStyle}" />
					<telerikMauiControls:RadBorder Grid.Row="1"
                                           Style="{StaticResource DataGridFilterControlSeparatorStyle_Mobile}" />
					<HorizontalStackLayout Grid.Row="2"
                                   HorizontalOptions="End"
                                   VerticalOptions="Center"
                                   Margin="{OnPlatform Android='0, 8, 0, 0', iOS='0, 10, 0, 0'}">
						<telerikMauiControls:RadButton Text="{telerikMauiControls:Localize DataGrid_Filter_ResetFilter}"
                                               Command="{TemplateBinding ResetFilterCommand}"
                                               Style="{StaticResource DataGridFilterControlResetFilterButtonStyle}"
                                               Margin="4, 0" />
						<telerikMauiControls:RadButton Text="{telerikMauiControls:Localize DataGrid_Filter_ApplyFilter}"
                                               Command="{TemplateBinding ApplyFilterCommand}"
                                               Style="{StaticResource DataGridFilterControlApplyFilterButtonStyle}"
                                               Margin="4, 0, 10, 0" />
					</HorizontalStackLayout>

				</Grid>
			</telerikMauiControls:RadBorder>
		</ControlTemplate>
	</ResourceDictionary>
</ContentPage.Resources>
<telerik:RadDataGrid x:Name="dataGrid"
                     Grid.Row="1"
                     UserEditMode="Cell"
                     AutoGenerateColumns="False"
                     ItemsSource="{Binding Items}">
	<telerik:RadDataGrid.Columns>
		<telerik:DataGridTextColumn PropertyName="Country"
									HeaderText="Country">
			<telerik:DataGridTextColumn.FilterControlTemplate>
				<DataTemplate>
					<telerik:DataGridTextFilterControl ControlTemplate="{StaticResource DataGridTextFilterControlControlTemplate_Mobile}" />
				</DataTemplate>
			</telerik:DataGridTextColumn.FilterControlTemplate>
		</telerik:DataGridTextColumn>


		<telerik:DataGridTextColumn PropertyName="Capital"
									HeaderText="Capital"/>
	</telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

## See Also

- [DataGrid Documentation](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview)
- [TelerikTheming Documentation](https://www.telerik.com/maui-ui/documentation/styling-and-themes/overview)
- [DataGrid Filtering Control Template](https://www.telerik.com/maui-ui/documentation/controls/datagrid/filtering/filter-control-template)
