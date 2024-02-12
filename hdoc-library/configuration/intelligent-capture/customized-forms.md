As well as standard Capture forms that are provided with each app, Hornbill also provides the ability to create your own customized forms. With custom forms, you can create multiple questions of different field types for users and customers to answer during Intelligent Capture.

## Node Properties
### Custom Form
* **Custom Form Name**<br>The display name for the node on the intelligent capture designer.
* **Purpose**<br>A text field to record the purpose of the custom form (optional).

### Form Settings
* **Language**<br>A default language version of the custom form is provided, but you can opt to create different language versions of the custom form by selecting another available language and populating the labels, answers in different languages.
* **Form Id**<br>This is the unique identifier for the custom form, this can be used later to identify the answers to your questions when using the Hornbill Business Process Workflow engine. The Form Id must be at least 3 characters in length.
* **Form Prompt**<br>This is any text you wish to appear with the custom form to help identify it's purpose.
* **Never Skip Form**<br>Setting to True will ensure that this form is never bypassed in your capture flow, even if custom questions have default values set and the questions are not set to mandatory. This will ensure the user will always be presented with the form to at least validate the default choices, or change them if required.

### Form Fields
The form fields are the questions you wish to ask on the custom from.
* You can add new questions by selecting the 'add field button
* You can edit an existing question by selecting the note and pencil icon of an existing question
* You can delete an existing question by using the trash can icon of an existing question
* You can re-order how the questions will appear by using the up and down arrows to move the questions into the required order.

## Field Properties
Field properties are specific for each field / question you wish to add to your custom form. If you require the questions of the custom form to be available in more than the default english languages, use the Properties Language option to switch the configuration into the additionally required languages and set the values accordingly - these translated values will then be presented to the user dependent on the language set in their profile when viewing the custom form questions.

There are various field options and setting and these are explained below.

* **Field Id**<br>This is the unique id for the question on the custom form. This can normally be left, unless you are wanting to map the answer from this question to a custom field on a request, where a field mapping needs to be given. Read about field mappings. The Field Id must be at least 3 characters in length.
* **Label**<br>This will be the label used to represent the question on the custom form.
* **Description**<br>You can use this field to provide hints / tips or advice on how to complete the answer to this specific question.

### Field Flags
#### Default Flags
* **Show this field in summary panel once form is completed**<br>Tick this option if you want the question and answer to appear on the right hand side confirmation panel during the progressive capture flow.
* **This field requires a value to be provided**<br>Tick this option is you want to make the answering of this question Mandatory.
* **This field will be visible on the form**<br>Tick this option if you want the field to be visible on the form - sometimes this is not needed, if you are passing a fixed value into a field and you can hide this from the user.
* **This field will be read only**<br>Tick this option if you wish to use the field to be for information only.
* **This field will be visible in read mode if it has no value**<br>Tick this option if you would like this field to be displayed, even if there is no value stored in it. Just the label will be shown.

#### Override Flags
The Override Flags allows you to set the conditions under which this field will be displayed. This can be based on the answer or entry on a previous field.

### Field Type Settings

#### Field Type
This specifies the type for the field you are adding

* **Single line text field**
    Use this option if you want to present the user with a single line input box.
* **Multi line text field**
    Use this option if you want to present the user with a multi-line input box.
Static checkbox group
Use this option if you want the user to select one or multiple values from a definable checkbox list
Pcf custom form output.png
Dynamic checkbox group
Use this option if you want the user to select one or multiple values from a pre-defined checkbox list, select a data provider and optionally filter the returned results
Simple List - Choose an existing simple list as your Data Provider
Data Query - Choose from a list of supplied data queries as your Data Provider (All Sites, My Sites, All Assets, Assets by Class, Assets by Type, All Users, Co-Workers, Basic Users)
Static drop down select box
Use this option if you want the user to select one option from a definable select box list
Dynamic drop down select box
Use this option if you want the user to select one option from a pre-defined select box list, select a data provider and optionally filter the returned results
Simple List - Choose an existing simple list as your Data Provider
Data Query - Choose from a list of supplied data queries as your Data Provider (All Sites, My Sites, All Assets, Assets by Class, Assets by Type, All Users, Co-Workers, Basic Users)

Static Radioset
Use this option if you want the user to select one option from a definable radio button set
Dynamic radioset
Use this option if you want the user to select one option from a pre-defined radio button set, , select a data provider and optionally filter the returned results
Simple List - Choose an existing simple list as your Data Provider
Data Query - Choose from a list of supplied data queries as your Data Provider (All Sites, My Sites, All Assets, Assets by Class, Assets by Type, All Users, Co-Workers, Basic Users)
Date Control
Use this option if you only require the user to provide a date
Date & Time Control
Use this option if you require the user to provide both a date and time
Orion user group picker
Use this option if you want the user to select a group or groups from the pre-defined organizational groupings
Label
Use this option if you want to add a separator into the questions being asked, or on the answers section of the request
Different field types will have different configuration options available to them, including:

Ability to set default values
Ability to define values for static checkbox, static select box, static radio set options (display name and value)
Regex Field Validation
Displaying Conditional Fields

This feature allows for the showing or hiding of fields on custom capture forms based on the answers to other questions on either the same custom capture form, or answers to questions on previous capture forms (conditions).

Add a new form field to a capture form and untick the This field will be visible on the form option under the Default Flags tab
A new Override flags tab will be visible next to the Default Flags, navigate here and select Add new condition
Give the condition a name and choose options such as This field will be visible on the form
Using the If the following is true option to add conditions under which this field will be shown / hidden, this can be based on a combination of values (answers) to other questions (fields) on the same or previous capture forms. Select apply Settings when finished.
It is possible to set multiple sets of Conditions under which a field may be shown. Simply add more conditions under the Override Flags tab using the Add new condition option
Where multiple conditions are listed, these will be evaluated from the top down until a match is found, the evaluation will stop here and no further conditions will be checked).
Complete the Field Type Settings options to define the attributes of the conditional field.