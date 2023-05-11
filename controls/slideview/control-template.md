---
title: Control Template
page_title: .NET MAUI SlideView Documentation - Control Template
description: "Learn about the visual appearence defined throught the control template."
position: 7
slug: slideview-control-template
---

# .NET MAUI SlideView Control Template

SlideView's visual appearance is defined through a Control Template. In order to customize the way the SlideView looks, you will need to take the default `ControlTemplate` and modify it.

This topic gives an overview of the ControlTemplate of the SlideView control, so you can copy it to your app and make changes.

```XAML
<ResourceDictionary>
            <Style x:Key="TouchableViewStyle" TargetType="VisualElement">
                <Setter Property="BackgroundColor" Value="Transparent" />
            </Style>

            <Style x:Key="TouchableViewStyle_Horizontal" TargetType="VisualElement" BasedOn="{StaticResource TouchableViewStyle}">
                <Setter Property="MinimumWidthRequest" Value="40" />
            </Style>

            <Style x:Key="TouchableViewStyle_Vertical" TargetType="VisualElement" BasedOn="{StaticResource TouchableViewStyle}">
                <Setter Property="MinimumHeightRequest" Value="40" />
            </Style>

            <Style x:Key="NavigationButtonStyle" TargetType="telerikMauiControls:RadButton">
                <Setter Property="CornerRadius" Value="{OnPlatform Default=4, iOS=8, Android=12}" />
                <Setter Property="FontFamily" Value="{Static telerik:TelerikFont.Name}" />
                <Setter Property="FontSize" Value="{OnPlatform Default=10, WinUI=14}" />
                <Setter Property="TextColor" Value="{AppThemeBinding Light=#B3000000, Dark=#B3FFFFFF}" />
                <Setter Property="BackgroundColor" Value="{AppThemeBinding Light=#F3F3F3, Dark=#1A1A1A}" />
                <Setter Property="BorderThickness" Value="0" />
                <Setter Property="Padding" Value="0" />
                <Setter Property="telerikMauiControls:NavigationButtonUtils.Visibility" Value="{Binding NavigationButtonsVisibility, Source={RelativeSource Mode=TemplatedParent}}" />
                <Setter Property="VisualStateManager.VisualStateGroups">
                    <VisualStateGroupList>
                        <VisualStateGroup x:Name="CommonStates">
                            <VisualState x:Name="Normal"/>
                            <VisualState x:Name="PointerOver">
                                <VisualState.Setters>
                                    <Setter Property="TextColor" Value="{AppThemeBinding Light= Black, Dark=White}"/>
                                </VisualState.Setters>
                            </VisualState>
                            <VisualState x:Name="Disabled">
                                <VisualState.Setters>
                                    <Setter Property="TextColor" Value="Black" />
                                </VisualState.Setters>
                            </VisualState>
                        </VisualStateGroup>
                    </VisualStateGroupList>
                </Setter>
            </Style>

            <Style x:Key="NavigationButtonStyle_Horizontal" TargetType="telerik:RadButton" BasedOn="{StaticResource NavigationButtonStyle}">
                <Setter Property="WidthRequest" Value="{OnPlatform Default=16, iOS=44, Android=40}" />
                <Setter Property="HeightRequest" Value="{OnPlatform Default=38, iOS=44, Android=40}" />
            </Style>

            <Style x:Key="NavigateToPreviousItem_Button_Style_Horizontal" TargetType="telerik:RadButton" BasedOn="{StaticResource NavigationButtonStyle_Horizontal}">
                <Setter Property="Text" Value="{x:Static TelerikFont.IconLeftDir}" />
                <Setter Property="Margin" Value="2, 0, 0, 0" />
            </Style>

            <Style x:Key="NavigateToNextItem_Button_Style_Horizontal" TargetType="telerik:RadButton" BasedOn="{StaticResource NavigationButtonStyle_Horizontal}">
                <Setter Property="Text" Value="{x:Static telerik:TelerikFont.IconRightDir}" />
                <Setter Property="Margin" Value="0, 0, 2, 0" />
            </Style>

            <Style x:Key="NavigationButtonStyle_Vertical" TargetType="telerik:RadButton" BasedOn="{StaticResource NavigationButtonStyle}">
                <Setter Property="WidthRequest" Value="{OnPlatform Default=38, iOS=44, Android=40}" />
                <Setter Property="HeightRequest" Value="{OnPlatform Default=16, iOS=44, Android=40}" />
            </Style>

            <Style x:Key="NavigateToPreviousItem_Button_Style_Vertical" TargetType="telerik:RadButton" BasedOn="{StaticResource NavigationButtonStyle_Vertical}">
                <Setter Property="Text" Value="{x:Static telerik:TelerikFont.IconUpDir}" />
                <Setter Property="Margin" Value="0, 2, 0, 0" />
            </Style>

            <Style x:Key="NavigateToNextItem_Button_Style_Vertical" TargetType="telerik:RadButton" BasedOn="{StaticResource NavigationButtonStyle_Vertical}">
                <Setter Property="Text" Value="{x:Static telerik:TelerikFont.IconDownDir}" />
                <Setter Property="Margin" Value="0, 0, 0, 2" />
            </Style>

            <Style x:Key="SlideViewIndicator_Style" TargetType="telerik:SlideViewIndicator">
                <Setter Property="Margin" Value="7" />
            </Style>

            <Style x:Key="SlideViewIndicator_Style_Horizontal" TargetType="telerik:SlideViewIndicator" BasedOn="{StaticResource SlideViewIndicator_Style}">
                <Setter Property="HorizontalOptions" Value="Center" />
                <Setter Property="VerticalOptions" Value="End" />
                <Setter Property="Grid.Row" Value="2" />
            </Style>

            <Style x:Key="SlideViewIndicator_Style_Vertical" TargetType="telerik:SlideViewIndicator" BasedOn="{StaticResource SlideViewIndicator_Style}">
                <Setter Property="HorizontalOptions" Value="End" />
                <Setter Property="VerticalOptions" Value="Center" />
                <Setter Property="Orientation" Value="Vertical" />
                <Setter Property="Grid.Column" Value="2" />
            </Style>

            <ControlTemplate x:Key="RadSlideView_ControlTemplate_Horizontal">
                <Grid BackgroundColor="Transparent"
              IsClippedToBounds="True"
              RowDefinitions="Auto, *, Auto">
                    <telerik:SlideViewContent x:Name="PART_SlideViewContent"
                                        Items="{Binding Items, Source={RelativeSource Mode=TemplatedParent}}"
                                        Spacing="{Binding Spacing, Source={RelativeSource Mode=TemplatedParent}}"
                                        HasLooping="{Binding HasLooping, Source={RelativeSource Mode=TemplatedParent}}"
                                        Orientation="Horizontal"
                                        Grid.Row="1" />
                    <StackLayout Style="{OnIdiom Phone={StaticResource TouchableViewStyle_Horizontal}, Tablet={StaticResource TouchableViewStyle_Horizontal}}"
                         Grid.Row="1"
                         HorizontalOptions="Start"
                         VerticalOptions="Center">
                        <View.GestureRecognizers>
                            <TapGestureRecognizer Command="{Binding NavigateToPreviousItemCommand, Source={RelativeSource Mode=TemplatedParent}}" />
                        </View.GestureRecognizers>
                        <telerik:RadButton Command="{Binding NavigateToPreviousItemCommand, Source={RelativeSource Mode=TemplatedParent}}"
                                               Style="{Binding ActualNavigateToPreviousItemButtonStyle, Source={RelativeSource Mode=TemplatedParent}}" />
                    </StackLayout>
                    <StackLayout Style="{OnIdiom Phone={StaticResource TouchableViewStyle_Horizontal}, Tablet={StaticResource TouchableViewStyle_Horizontal}}"
                         HorizontalOptions="End"
                         VerticalOptions="Center"
                         Grid.Row="1">
                        <View.GestureRecognizers>
                            <TapGestureRecognizer Command="{Binding NavigateToNextItemCommand, Source={RelativeSource Mode=TemplatedParent}}" />
                        </View.GestureRecognizers>
                        <telerik:RadButton Command="{Binding NavigateToNextItemCommand, Source={RelativeSource Mode=TemplatedParent}}"
                                               Style="{Binding ActualNavigateToNextItemButtonStyle, Source={RelativeSource Mode=TemplatedParent}}" />
                    </StackLayout>
                    <telerik:SlideViewIndicator ItemsSource="{Binding IndicatorItemsSource, Source={RelativeSource Mode=TemplatedParent}}"
                                          CurrentIndex="{Binding CurrentIndex, Source={RelativeSource Mode=TemplatedParent}}"
                                          HasLooping="{Binding HasLooping, Source={RelativeSource Mode=TemplatedParent}}"
                                          Style="{Binding ActualIndicatorStyle, Source={RelativeSource Mode=TemplatedParent}}" />
                </Grid>
            </ControlTemplate>

            <ControlTemplate x:Key="RadSlideView_ControlTemplate_Vertical">
                <Grid BackgroundColor="Transparent"
              IsClippedToBounds="True"
              ColumnDefinitions="Auto, *, Auto">
                    <telerik:SlideViewContent x:Name="PART_SlideViewContent"
                                        Items="{Binding Items, Source={RelativeSource Mode=TemplatedParent}}"
                                        Spacing="{Binding Spacing, Source={RelativeSource Mode=TemplatedParent}}"
                                        HasLooping="{Binding HasLooping, Source={RelativeSource Mode=TemplatedParent}}"
                                        Orientation="Vertical"
                                        Grid.Column="1" />
                    <StackLayout Style="{OnIdiom Phone={StaticResource TouchableViewStyle_Vertical}, Tablet={StaticResource TouchableViewStyle_Vertical}}"
                         Grid.Column="1"
                         HorizontalOptions="Center"
                         VerticalOptions="Start">
                        <View.GestureRecognizers>
                            <TapGestureRecognizer Command="{Binding NavigateToPreviousItemCommand, Source={RelativeSource Mode=TemplatedParent}}" />
                        </View.GestureRecognizers>
                        <telerik:RadButton Command="{Binding NavigateToPreviousItemCommand, Source={RelativeSource Mode=TemplatedParent}}"
                                               Style="{Binding ActualNavigateToPreviousItemButtonStyle, Source={RelativeSource Mode=TemplatedParent}}" />
                    </StackLayout>
                    <StackLayout Style="{OnIdiom Phone={StaticResource TouchableViewStyle_Vertical}, Tablet={StaticResource TouchableViewStyle_Vertical}}"
                         Grid.Column="1"
                         HorizontalOptions="Center"
                         VerticalOptions="End">
                        <View.GestureRecognizers>
                            <TapGestureRecognizer Command="{Binding NavigateToNextItemCommand, Source={RelativeSource Mode=TemplatedParent}}" />
                        </View.GestureRecognizers>
                        <telerik:RadButton Command="{Binding NavigateToNextItemCommand, Source={RelativeSource Mode=TemplatedParent}}"
                                               Style="{Binding ActualNavigateToNextItemButtonStyle, Source={RelativeSource Mode=TemplatedParent}}" />
                    </StackLayout>
                    <telerik:SlideViewIndicator ItemsSource="{Binding IndicatorItemsSource, Source={RelativeSource Mode=TemplatedParent}}"
                                          CurrentIndex="{Binding CurrentIndex, Source={RelativeSource Mode=TemplatedParent}}"
                                          HasLooping="{Binding HasLooping, Source={RelativeSource Mode=TemplatedParent}}"
                                          Style="{Binding ActualIndicatorStyle, Source={RelativeSource Mode=TemplatedParent}}" />
                </Grid>
</ControlTemplate>
</ResourceDictionary>
```