---
title: Commands
page_title: .NET MAUI NumericInput Documentation | Commands
description: Check our &quot;Commands&quot; documentation article for Telerik NumericInput for .NET MAUI control
position: 9
previous_url: /controls/numericinput/numericinput-commands
slug: numericinput-commands
---

# Commands

The NumericInput exposes `IncreaseCommand` and `DecreaseCommand` which could be used to define custom functionality upon the respective actions. These commands allow you to easily change and extend the control's default behavior.

In the next example, you can see how the NumericInput commands could be utilized in order to implement auto-reverse functionality – start from the Minimum value when the Maximum is reached and vice versa.

1. First, create the `ViewModel` with both `IncreaseCommand` and `DecreaseCommand` implementations:

 ```C#
public class CommandsViewModel : NotifyPropertyChangedBase
{
    private double value;
    
    public CommandsViewModel()
    {
        this.CustomIncreaseCommand = new Command(this.IncreaseCommandExecute, this.IncreaseCommandCanExecute);
        this.CustomDecreaseCommand = new Command(this.DecreaseCommandExecute, this.DecreaseCommandCanExecute);
        this.Step = 2;
        this.Value = 0;
        this.Minimum = 0;
        this.Maximum = 6;
    }
    
    public double Maximum { get; set; }
    
    public double Minimum { get; set; }
    
    public double Step { get; set; }
    
    public double Value
    {
        get
        {
            return this.value;
        }
        set
        {
            if (this.value != value)
            {
                this.UpdateValue(ref this.value, value);
            }
        }
    }
    
    public ICommand CustomDecreaseCommand { get; set; }
    
    public ICommand CustomIncreaseCommand { get; set; }
    
    private bool DecreaseCommandCanExecute(object arg)
    {
        return true;
    }
    
    private void DecreaseCommandExecute(object obj)
    {
        double newValue = this.Value - this.Step;
        if (newValue >= this.Minimum)
            this.Value = newValue;
        else
            this.Value = this.Maximum;
    }
    
    private bool IncreaseCommandCanExecute(object arg)
    {
        return true;
    }
    
    private void IncreaseCommandExecute(object obj)
    {
        double nextValue = this.Value + this.Step;
        if (nextValue <= this.Maximum)
            this.Value = nextValue;
        else
            this.Value = this.Minimum;
    }
}
 ```

1. Define the NumericInput with the respective bindings:

 ```XAML
 <telerik:RadNumericInput x:Name="input"
					      Minimum="{Binding Minimum}"
					      Maximum="{Binding Maximum}"
					      Step="{Binding Step}"
					      Value="{Binding Value, Mode=TwoWay}"                                    
					      IncreaseCommand="{Binding CustomIncreaseCommand}"
					      DecreaseCommand="{Binding CustomDecreaseCommand}">
    <telerik:RadNumericInput.BindingContext>
        <local:CommandsViewModel />
    </telerik:RadNumericInput.BindingContext>
</telerik:RadNumericInput>
 ```

 In the example:

 ```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
 ```

>tip For a demo, refer to the **NumericInput/Features/Commands** folder of the SDK Browser MAUI application.

## See Also

- [Globalization]({%slug numericinput-globalization%})
