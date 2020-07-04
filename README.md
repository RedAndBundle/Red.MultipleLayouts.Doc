# Multiple Report Layout Selector
Automatic report layout selection for Business Central reports.

## Introduction
Do you need to print different report layouts based on different situations? But you don't want your users to have to select these at the time of printing. Red and Bundle's Multiple Report Layout Selector will give you a smooth reporting experience.

The Multiple Report Layout Selector will automatically select the correct report layout to use based on dimension, customer, vendor, or any other data in your system. The Multiple Report Layout Selector will work with Word, RDLC, and ForNAV report layouts.

Try it today and impress your clients with an easy and intuitive way of selecting the correct report layout.

## Business Logic
If there are one or less Custom Report Layouts for the current report Business Central will print the default layout.
If there are more than one Custom Report layouts for the current report and one applicable entry in the setup table Business Central will use that layout.
If there are more than one Custom Report layouts for the current report but no entries in the setup table Business Central will let the user choose which layout to use.
If there are more than one Custom Report layouts for the current report and  more than one applicable entries in the setup table Business Central will let the user choose which of the applicable entries to use.

## Setup
To select the layout you want to use please navigate to "Red Layout Selection". In this page you can select reports and the condition on which layouts are selected

> Please make sure the Table No. matches the record you want to print with the report.

![SetupPage](_media/Screenshot&#32;Layout&#32;Selection.png)


| Field | Description |
| --- | --- |
| Report ID | Select the report number from the full list of installed reports |
| Table No. | Select the table the report is run from. For instance the Sales Invoice uses table 112, the Sales Order uses table 36 etc. |
| Field No. | Use the field that you want to use to determine whether or not to use the Custom Report Layout |
| Value | The value of the field that determines if the Custom Report Layout should be used |
| CustomLayoutDescription | The Custom Report Layout to use |