---
title: Keyboard Support
page_title: .NET MAUI ComboBox Documentation - Keyboard Support for WinUI and MacCatalyst
description: Learn more about the available keyboard combinations as part of the supported Telerik UI for .NET MAUI ComboBox accessibility standards.
position: 6
slug: combobox-keyboard-support
---

# .NET MAUI ComboBox Keyboard Support

The [Telerik UI for .NET MAUI ComboBox]({%slug combobox-overview%}) provides keyboard navigation support on `WinUI` and `MacCatalyst`.

>important Keyboard support is available only on .NET 8.0.

The following table lists the actions and keyboard combinations that are available in the ComboBox:

| Hotkey Combinations  | Action |
| -------------------- | ------ |
| `F4` | Shows the drop-down if it is closed. If the drop-down is opened pressing the F4 key will submit the selection and close the drop-down. |
| `Up Arrow` / `Down Arrow` | If the drop-down is opened, pressing Up/Down Arrows will change the highlighted item in the drop-down list. If it is closed pressing Up/Down Arrows will change the SelectedItem.|
| `Left Arrow` / `Right Arrow` | If the drop-down is opened, pressing Left/Right Arrows will change the highlighted item in the drop-down list. If it is closed pressing Left/Right Arrows will change the SelectedItem. They work only when `IsEditable` is `False`. |
| `Enter` |Takes effect only when the drop-down of the ComboBox is opened. Commits the selection and closes the drop-down. |
| `Esc`	| Takes effect only when the drop-down is opened. It cancels the selection and closes the drop-down of the ComboBox.`Esc` key is not supported in MacOS when `IsEditable` is `True`. |
| `Home` / `End` | Works only when `IsEditable` is `False`. When the drop-down is opened pressing the Home/End keys will change the highlighted item to the first/last item. If the drop-down is closed pressing the Home/End keys will change the selected item to the first/last item.|
| `PageUp` / `PageDown` | Pressing any of these keys will open the drop-down when it is closed. If the drop-down is opened pressing PageUp/PageDown will change the highlighted item. |

>On MacOS when `IsEditable` property of the ComboBox is `True`, `Command` key should be pressed to enable the previously described hotkeys.

To enable the keyboard support when the drop-down is opened and when setting the custom item and selected item templates in ComboBox for .NET MAUI, wrap the content of the templates in a `RadComboBoxItem`. Define the necessary visual states of the `RadComboBoxItem`, specifically `MouseOver` and `Highlighted`.

Here is a sample comboBox definition in XAML:

```XAML
<telerik:RadComboBox ItemsSource="{Binding Items}" 
                     DisplayMemberPath="Name" 
                     x:Name="combo"
                     Placeholder="Select City">
    <telerik:RadComboBox.ItemTemplate>
        <DataTemplate>
            <telerik:RadComboBoxItem>
                <VisualStateManager.VisualStateGroups>
                    <VisualStateGroup x:Name="CommonStates">
                        <VisualState x:Name="Normal"/>
                        <VisualState x:Name="MouseOver">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadComboBoxItem.BackgroundColor" Value="LightGray"/>
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState Name="Highlighted">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadComboBoxItem.BackgroundColor" Value="LightGray" />
                            </VisualState.Setters>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateManager.VisualStateGroups>
                <Label Text="{Binding Name}"
                       Padding="8, 7, 0, 7"
                       TextColor="Black"/>
            </telerik:RadComboBoxItem>
        </DataTemplate>
    </telerik:RadComboBox.ItemTemplate>
    <telerik:RadComboBox.SelectedItemTemplate>
        <DataTemplate>
            <telerik:RadComboBoxItem>
                <VisualStateManager.VisualStateGroups>
                    <VisualStateGroup x:Name="CommonStates">
                        <VisualState x:Name="Normal"/>
                        <VisualState x:Name="MouseOver">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadComboBoxItem.BackgroundColor" Value="LightGray"/>
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState Name="Highlighted">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadComboBoxItem.BackgroundColor" Value="LightCoral" />
                            </VisualState.Setters>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateManager.VisualStateGroups>
                <VerticalStackLayout>
                    <Label Text="{Binding Name}"
                           Padding="8, 7, 0, 7"
                           TextColor="Black"/>
                    <Label Text="{Binding Population}"
                           FontSize="12"
                           Padding="8, 7, 0, 7"/>
                </VerticalStackLayout>
            </telerik:RadComboBoxItem>
        </DataTemplate>
    </telerik:RadComboBox.SelectedItemTemplate>
</telerik:RadComboBox>
```

## See Also

- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})
