#### 00 Getting Started with Scheduler
Scheduler is a widget that displays appointments and allows users to manage them. 

This tutorial shows how to configure basic Scheduler features. As a result, you will get the following widget:

[widget]

Refer to the subtopics for details on each configuration step. You can also see the full code below or download it from the following GitHub repository: [getting-started-with-scheduler].


#### 02 Create a DataGrid
[Add DevExtreme to your jQuery application](/Documentation/Guide/jQuery_Components/Add_DevExtreme_to_a_jQuery_Application/) and use the following code to create a **Scheduler**:


#### 05 Bind the Scheduler to Data
The Scheduler can load and update data from these data source types:

* Local array;

* Read-Only Data in JSON Format;

* OData;

* Web API, PHP, MongoDB;

* Custom data source.

Use the dataSource option to specify a data source. In this tutorial, we use a local array of SchedulerAppointment objects. 

The widget supports three types of appointments: one-time, all-day, and recurring. The used data source contains them all. 

[code]

Run the code and ensure that the widget properly displays all appointments.

#### 10 Enable Additional Views
A view defines the time interval for which to display appointments. The following view types are supported:

* [Day](/Documentation/Guide/Widgets/Scheduler/Views/View_Types/#Day_View) (default);

* [Week and WorkWeek](/Documentation/Guide/Widgets/Scheduler/Views/View_Types/#Week_and_WorkWeek_Views) (week is added by default);

* [Month](/Documentation/Guide/Widgets/Scheduler/Views/View_Types/#Month_View);

* [Timeline](/Documentation/Guide/Widgets/Scheduler/Views/View_Types/#Timeline_Views);

* [Agenda](/Documentation/Guide/Widgets/Scheduler/Views/View_Types/#Agenda_View);

* [Custom](/Documentation/Guide/Widgets/Scheduler/Views/Customize_Individual_Views/).

Use the views option to specify these views: "day", "week", "month", and "timelineWeek".

[code]


#### 15 Edit Appointments
Users can open an appointment form to update or remove the appointment. They can also remove appointments and change their start and end dates in the grid. Use the editing object to configure allowed editing operations. 

In this step, we will forbid users to drag the appointments.

[code]



#### 20 Group Appointments  
We will group appointments by priority. For this, do the following:
1. Create a resource kind. In this example, this is the `priorities` array. It consists of objects each of which defines a priority category: sets its heading, color, and id. 
2. Use the resources array to add a resource kind: specify the fieldExpr and dataSource fields in the resource object. By this moment, the appointments will be painted based on the priority.
3. Use the groups option to specify the field by which appointments are categorized by priority.

[code]

If you run this code, you will see the Scheduler grid is split into two columns. Each column displays appointments of either low or high priority.

#### 25 Time Zone Support
Scheduler displays all appointments in the client time zone. To change this default behavior, you can specify a different time zone in the timeZone option. It accepts values from the IANA database. In this tutorial, the 'Europe/Berlin' time zone is used.

Additionally, we will allow users to edit time zones of individual appointments. For this, enable the editing.allowTimeZoneEditing option.

#### 30 Enable Adaptive Mode
Since people use portable devices to work with Scheduler, it should change its interface accordingly. Set the adaptivityEnabled option to true and see how the Scheduler adapts its interface. 

[code]

You have now configured the basic Scheduler features. For more details on this widget, explore the following resources:

* [Demos](https://js.devexpress.com/Demos/WidgetsGallery/Demo/Scheduler/Overview/)

* [API Reference](/Documentation/ApiReference/UI_Widgets/dxScheduler/)