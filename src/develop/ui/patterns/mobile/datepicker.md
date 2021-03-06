---
tags: runtime-mobileandreactiveweb;  
summary: 
---

# DatePicker Pattern

The DatePicker pattern provides you with a date and time picker with a flat UI to display inline on the screen. It can receive lists of dates with events and it enables you have a selection within a range of days. The DatePicker was created using the [Pikaday.js
library](https://github.com/dbushell/Pikaday/blob/master/README.md "https://github.com/dbushell/Pikaday/blob/master/README.md") .

You can use this pattern to display a list of elements side by side, with a different number of items per row on different devices.

## How to Use the DatePicker Pattern

Use static data or a **List** widget inside this block to display items in a gallery pattern.

![](images/datepicker.png?width=600)  

1\. Upon dragging the DatePicker to the page, you'll be prompted to create an
event.

![](images/datepicker_create_an_event.png?width=500)

2\. To have access to the picked date, you need to create an assign to the
**startDate** (if SelectInterval is False ).

3\. Set the default value of the variable **PickedDate** as CurrDateTime().

![](images/datepicker_start.png)

**Result**:

![](images/datepicker_BasicExample.gif)

### Listing Events of a Selected Day

1\. Set the area where you want to put the list of events.

![](images/add_new_date.png)

2\. Create an entity with a **DateTime** attribute.

3\. Set the entity in your **EventList** parameter on eventList, using the
right attribute to map.

![](images/interaction_datepicker.png)  

4\. Add the list to the page.

![](images/date_time.png)  

5\. Create a Local Variable.

![](images/date_local_variable.png)  

6\. Get another Aggregate for the Events and set a filter on the aggregate:  
DateTimeToDate(Events.DateTime) = Date

![](images/datepicker_filter.png)

**Result**:

![](images/datepicker_Profit.gif) 

## Input Parameters

| **Input Name** |  **Description** |  **Default Value** |
|---|---|---|
| ![](images/input.png)  EventList  |  Receives a List of DateTime records that are used to highlight days as event days. |  none |
| ![](images/input.png) MinDate  |  Days before this date will be disabled. |  none  |
| ![](images/input.png) MaxDate  |  Days after this date will be disabled.  | none |  
| ![](images/input.png) InitialDate  |  The initially selected day for the DatePicker. If not set, it will be the current day by default.  |  Current Date | 
| ![](images/input.png) ShowWeekNumbers  |  Displays the week number on the left side of the DatePicker.  |  True  |
| ![](images/input.png) FirstWeekDay  |  Defines which weekday should be displayed first. %%  0: Sunday %% 1: Monday %% 2: Tuesday %% 3: Wednesday %% 4: Thursday %% 5: Friday %% 6: Saturday | 1 |
| ![](images/input.png) ShowTime  |  Displays a time picker below the DatePicker.  |  False |  
| ![](images/input.png) Show24HourFormat  |  Changes the time picker to a 24-hour format.  |  True  |
| ![](images/input.png) DisabledDaysList  |  Receives a List of DateTime records that will be disabled on the DatePicker. If this parameter is not set, all days between the MinDate and MaxDate are enabled. No default value.  |  none |  
| ![](images/input.png) DisabledWeekDays  |  String containing disabled weekdays. If the string is empty, all weekdays are active. Example with Sunday and Friday disabled: "0,5,6". %% 0: Sunday %% 1: Monday %% 2: Tuesday %% 3: Wednesday %% 4: Thursday %% 5: Friday %% 6: Saturday  |  none  |
|![](images/input.png) SelectInterval  |  Allows the selection between two dates. If set to True, the Block Event "On Select" has the values for both parameters.  |  False |  
  
## Events

| **Event Name** |  **Description** |  **Mandatory**  |
| ---|---|--- |  
| ![](images/Event.png) OnSelect | Action to execute after selecting a DatePicker day. If SelectInterval is enabled, both parameters return values. If not, only the StartDate has a value.  |  True  |
  
## Layout and Classes

![](images/datepicker_layout_classes.png?width=700)

## CSS Selectors

| **Element** |  **CSS Class** |  **Description**  |
| ---|---|---  
| ![](images/css_selector.png) td |  .is-selected  |  Clicked day.  
| ![](images/css_selector.png) td  |  .is-startrange  |  If SelectInterval is True , this class will be the start range value.  |
