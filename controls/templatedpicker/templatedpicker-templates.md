---
title: Templates
page_title: .NET MAUI TemplatedPicker Documentation | Templates
description: Check our &quot;Templates&quot; documentation article for Telerik TemplatedPicker for .NET MAUI control.
position: 3
slug: templatedpicker-templates
---

# Templates

TemplatedPicker for .NET MAUI provides the following templates:

* `SelectorTemplate`(*ControlTemplate*): Defines the template used for displaying the selector of the picker.

* `PlaceholderTemplate`(*ControlTemplate*): Defines the template visualized for the placeholder.  

* `DisplayTemplate`(*ControlTemplate*): Defines the template visualized when an item from the selector was picked.

Using `SelectorSettings` property(of type *Telerik.XamarinForms.Input.PickerPopupSelectorSettings*) you can define the following templates:

* `HeaderTemplate`(*ControlTemplate*): Defines what will be displayed inside the dialog(popup) header.

* `FooterTemplate`(*ControlTemplate*): Defines what will be displayed inside the dialog(popup) footer.

### Example

Here is a sample TemplatedPicker definition:

<snippet id='templatedpicker-keyfeatures' />
```XAML
<telerikInput:RadTemplatedPicker SelectedValue="{Binding FromCity, Mode=TwoWay}"
								 DisplayMemberPath="Name"
								 SelectorTemplate="{StaticResource SelectorTemplate}">
	<telerikInput:RadTemplatedPicker.SelectorSettings>
		<telerikInput:PickerPopupSelectorSettings HeaderTemplate="{StaticResource HeaderTemplate}"/>
	</telerikInput:RadTemplatedPicker.SelectorSettings>
</telerikInput:RadTemplatedPicker>
```

## Selector Template

Here is a sample definition of the SelectorTemplate:

<snippet id='templatedpicker-keyfeatures-selectortemplate' />
```XAML
<ControlTemplate x:Key="SelectorTemplate">
	<Grid HeightRequest="250">
		<Grid.ColumnDefinitions>
			<ColumnDefinition />
			<ColumnDefinition />
		</Grid.ColumnDefinitions>
		<telerikDataControls:RadSpinner Grid.Column="0"
										ItemsSource="{Binding Countries}"
										SelectedItem="{Binding FromCountry, Mode=TwoWay}"
										DisplayMemberPath="Name" />
		<telerikDataControls:RadSpinner Grid.Column="1"
										ItemsSource="{Binding FromCountry.Cities}"
										SelectedItem="{TemplateBinding SelectedValue}"
										DisplayMemberPath="Name" />
	</Grid>
</ControlTemplate>
```

## Header Template:

<snippet id='templatedpicker-keyfeatures-headertemplate' />
```XAML
<ControlTemplate x:Key="HeaderTemplate">
	<Grid BackgroundColor="DarkGray">
		<Grid.ColumnDefinitions>
			<ColumnDefinition />
			<ColumnDefinition />
		</Grid.ColumnDefinitions>
		<Label Text="Origin Country"
			   HorizontalOptions="Center"
			   VerticalOptions="Center"
			   TextColor="White" />
		<Label Grid.Column="1"
			   Text="Origin City" 
			   HorizontalOptions="Center"
			   VerticalOptions="Center"
			   TextColor="White" />
	</Grid>
</ControlTemplate>
```

add the following data item for the first spinner:

<snippet id='templatedpicker-country-businessmodel' />
```C#
public class Country : NotifyPropertyChangedBase
{
	private string name;

	public Country()
	{
		this.Cities = new ObservableCollection<City>();
	}

	public string Name
	{
		get
		{
			return this.name;
		}
		set
		{
			if (value != this.name)
			{
				this.UpdateValue(ref this.name, value);
			}
		}
	}

	public ObservableCollection<City> Cities { get; }
}
```

add the following data item for the second spinner:

<snippet id='templatedpicker-city-businessmodel' />
```C#
public class City : NotifyPropertyChangedBase
{
	private string name;

	public string Name
	{
		get
		{
			return this.name;
		}
		set
		{
			if (value != this.name)
			{
				this.UpdateValue(ref this.name, value);
			}
		}
	}
}
```

here is a sample definition of the ViewModel:

<snippet id='templatedpicker-viewmodel' />
```C#
public class LocationViewModel : NotifyPropertyChangedBase
{
	private Country fromCountry;
	private City fromCity;

	public LocationViewModel()
	{
		this.Countries = new ObservableCollection<Country>
		{
			new Country
			{
				Name = "Austria",
				Cities =
				{
					new City { Name = "Graz" },
					new City { Name = "Innsbruck" },
					new City { Name = "Linz" },
					new City { Name = "Ratz" },
					new City { Name = "Salzburg" },
					new City { Name = "Vienna" },
					new City { Name = "Wolfsberg" },
					new City { Name = "Zeltweg" }
				}
			},
			new Country
			{
				Name = "Belgium",
				Cities =
				{
					new City { Name = "Antwerp" },
					new City { Name = "Assesse" },
					new City { Name = "Bruges" },
					new City { Name = "Charleroi" },
					new City { Name = "Lint" },
					new City { Name = "Ranst" },
					new City { Name = "Schaffen" },
					new City { Name = "Veurne" },
					new City { Name = "Zingem" },
				}
			},
			new Country
			{
				Name = "Denmark",
				Cities =
				{
					new City { Name = "Aalborg" },
					new City { Name = "Aarhus" },
					new City { Name = "Billund" },
					new City { Name = "Copenhagen" },
					new City { Name = "Karup" },
					new City { Name = "Odense" },
					new City { Name = "Viborg" },
					new City { Name = "Vojens" }
				}
			},
			new Country
			{
				Name = "France",
				Cities =
				{
					new City { Name = "Aurillac" },
					new City { Name = "Belley" },
					new City { Name = "Bourg-en-Bresse" },
					new City { Name = "Carcassonne" },
					new City { Name = "Caen" },
					new City { Name = "Deauville" },
					new City { Name = "La Rochelle" },
					new City { Name = "Nice" },
					new City { Name = "Marseille" },
					new City { Name = "Paris - Val-De-Marne" },
					new City { Name = "Paris - Val d'Oise" },
					new City { Name = "Rodez" }
				}
			},
			new Country
			{
				Name = "Germany",
				Cities =
				{
					new City { Name = "Baden-Baden" },
					new City { Name = "Berlin" },
					new City { Name = "Borkum" },
					new City{ Name = "Bremen" },
					new City{ Name = "Dortmund" },
					new City{ Name = "Dresden" },
					new City{ Name = "Hamburg" },
					new City{ Name = "Hannover" },
					new City{ Name = "Leipzig" },
					new City{ Name = "Mannheim" },
					new City{ Name = "Munich" },
					new City{ Name = "Nuremberg" }
				}
			},
			new Country
			{
				Name = "Italy",
				Cities =
				{
					new City { Name = "Aosta" },
					new City { Name = "Bari" },
					new City { Name = "Bologna" },
					new City { Name = "Parma" },
					new City { Name = "Rimini" },
					new City { Name = "Rome - Fiumicino" },
					new City { Name = "Rome - Ciampino" }
				}
			},
			new Country
			{
				Name = "Netherlands",
				Cities =
				{
					new City { Name = "Amsterdam" },
					new City { Name = "Bonaire" },
					new City { Name = "Eindhoven" },
					new City { Name = "Maastricht" },
					new City { Name = "Rotterdam" }
				}
			},
			new Country
			{
				Name = "Portugal",
				Cities =
				{
					new City { Name = "Braga" },
					new City { Name = "Cascais" },
					new City { Name = "Lisbon" },
					new City { Name = "Porto" }
				}
			},
			new Country
			{
				Name = "Spain",
				Cities =
				{
					new City { Name = "Alicante" },
					new City { Name = "Barcelona" },
					new City { Name = "Madrid" },
					new City { Name = "Seville" },
					new City { Name = "Valencia" },
					new City { Name = "Zaragoza" }
				}
			},
			new Country
			{
				Name = "United Kingdom",
				Cities =
				{
					new City { Name = "Bristol Airport" },
					new City { Name = "Castle Donington" },
					new City { Name = "Liverpool" },
					new City { Name = "London City Airport" },
					new City { Name = "London Luton" },
					new City { Name = "Manchester Airport" },
					new City { Name = "Norwich" },
					new City { Name = "Southampton" }
				}
			},
		};
	}

	public Country FromCountry
	{
		get
		{
			return this.fromCountry;
		}
		set
		{
			if (value != this.fromCountry)
			{
				this.UpdateValue(ref this.fromCountry, value);
			}
		}
	}

	public City FromCity
	{
		get
		{
			return this.fromCity;
		}
		set
		{
			if (value != this.fromCity)
			{
				this.UpdateValue(ref this.fromCity, value);
			}
		}
	}

	public ObservableCollection<Country> Countries { get; }
}
```

Set thus defined LocationViewModel as a BindingContext of the page:

```C#
this.BindingContext = new LocationViewModel();
```

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

This is the TemplatedPicker visual structure:

![TemplatedPicker](images/templated_picker_visual_structure.png)

## See Also

- [Styling]({%slug templatedpicker-styling%})
