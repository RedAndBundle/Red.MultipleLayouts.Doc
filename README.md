# Multiple Report Layout Selector
Automatic report layout selection for Microsoft Dynamics 365 Business Central reports.

## Introduction
Do you need to print different report layouts based on different situations? But you don't want your users to have to select these at the time of printing. Red and Bundle's Multiple Report Layout Selector will give you a smooth reporting experience.

The Multiple Report Layout Selector will automatically select the correct report layout to use based on dimension, customer, vendor, or any other data in your system. The Multiple Report Layout Selector will work with Word, RDLC, and ForNAV report layouts.

Try it today and impress your clients with an easy and intuitive way of selecting the correct report layout.

## Business Logic
If there are one or less Custom Report Layouts for the current report Dynamics 365 Business Central will print the default layout. When no Custom Layout is selected for the default layout the built-in report layout will be used.
If there are more than one Custom Report layouts for the current report and one applicable entry in the setup table Dynamics 365 Business Central will use that layout.
If there are more than one Custom Report layouts for the current report and more than one applicable entry in the setup table Dynamics 365 Business Central let the user choose which of these layouts to use.
If there are more than one Custom Report layouts for the current report and one entry marked as default in the setup table Dynamics 365 Business Central will use that default layout.
If there are more than one Custom Report layouts for the current report but no entries in the setup table Dynamics 365 Business Central will let the user choose which layout to use.

## Setup
To select the layout you want to use please navigate to "Red Layout Selection". In this page you can select reports and the condition on which layouts are selected

> Please make sure the Table No. matches the record you want to print with the report.

![SetupPage](./_media/Screenshot%20Setup.png)


| Field | Description |
| --- | --- |
| Report ID | Select the report number from the full list of installed reports. |
| Default   | Sets the layout to be the default fall back to be used if no definite match exists. |
| Table No. | Select the table the report is run from. For instance the Sales Invoice uses table 112, the Sales Order uses table 36 etc. |
| Field No. | Use the field that you want to use to determine whether or not to use the Custom Report Layout. |
| Value | The value of the field that determines if the Custom Report Layout should be used. |
| CustomLayoutDescription | The Custom Report Layout to use. Can only be empty when the line is default. |

### Printing checks
It is possible to use the Multiple Report Layout selection with the Reports ForNAV MICR check. To use a different report layout per bank account you will need to set up a Payment Journal per bank account and select the correct layouts in the Red Layout Selection.

![CheckLayoutPerBankAccount](./_media/Screenshot%20Check%20Selection.png)

## Recorder
If you are not sure which report and which source table you need to use you can switch on the recorder. If the recorder has been switched on the running of reports will create a new record in the Red Layout Selection with the Report Id and Table No. filled in.

![Recorder](./_media/Screenshot%20Record.png)
## Export
To export the Red Layout Selection you can select Export on the lint. This will export all the selected records to a json file.

![Export](./_media/Screenshot%20Export.png)

## Import
To import records from a json file you can select Import on the lint in the Red Layout Selection. This will import new records in the database.

![Export](./_media/Screenshot%20Import.png)

If the record already exists it will be skipped. If the Custom Report Layout in the import file does not exist it will be created. The custom layout will be a copy from the built in layout, you will need to import your Custom Report Layouts separately.

The structure of the import file looks like this:
```json
[
	{
		"Report ID":50000,
		"Custom Report Layout Code":"50000-000001",
		"Table No.":112,
		"Field No.":2,
		"Value":"10000"
	},
	{
		"Report ID":50000,
		"Custom Report Layout Code":"50000-000002",
		"Table No.":112,
		"Field No.":2,
		"Value":"20000"
	}
]
```

## Permissions
The Multiple Report Layout Selector comes with two permission levels, user and administrator. The user needs permission to read from the Red Layout Selection table. The Administrators also need permission to edit that table.

User permissions are assigned automatically to the "D365 BUS PREMIUM" and "D365 BASIC" permission sets. Administrator permissions need to be assigned manually by adding the "RED LAYOUT ADMINISTR" permission set to the user.

