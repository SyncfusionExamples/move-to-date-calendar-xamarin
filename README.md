# How to navigate to the specific month in Xamarin.Forms Calendar (SfCalendar)

Visible dates can be moved to specific date using [MoveToDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~MoveToDate.html) property available in [SfCalendar](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms_namespace.html?_ga=2.252324169.1541144887.1595824829-262160713.1529557470). It is applicable for all the [ViewMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~ViewMode.html).

**STEP 1:**  Create a ViewModel class and add a  **MoveToDate**  property with specific date.

``` c#
public class ViewModel : INotifyPropertyChanged
{
   public event PropertyChangedEventHandler PropertyChanged;

   private DateTime moveToDate = new DateTime(2010, 10, 12);

   public DateTime MoveToDate
   {
     get
     {
          return this.moveToDate;
     }
     set
     {
          this.moveToDate = value;
          this.OnPropertyChanged("MoveToDate");
     }
   }

   public ViewModel()
   {
   }

   private void OnPropertyChanged(string propertyName)
   {
                this.PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
   }
}
```

**STEP 2:**  Bind the MoveToDate ViewModel property to the [MoveToDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms.SfCalendar~MoveToDate.html) property of [SfCalendar](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms~Syncfusion.SfCalendar.XForms_namespace.html).

``` xml
<calendar:SfCalendar x:Name="calendar"
                             DataSource="{Binding Appointments}"
                             MoveToDate="{Binding MoveToDate}">
            <calendar:SfCalendar.BindingContext>
                <local:ViewModel/>
            </calendar:SfCalendar.BindingContext>
</calendar:SfCalendar>
```
**Output**

![MoveToDate](https://github.com/SyncfusionExamples/move-to-date-calendar-xamarin/blob/master/ScreenShot/MoveToDate.png) 
