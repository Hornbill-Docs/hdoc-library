This feature allows for the change field default flags properties on custom capture forms based on the answers to other questions on either the same custom capture form, or answers to questions on previous capture forms.
**In short to make it happen you need to define conditions and flags that will be overwritten once condition will be evaluated as true.**

### Field "Default flags" section

Every field has a set of flags:
* Required
* Visibility
* Read only
* Visibility for read only field without value (empty field)

<img src="/_books/hdoc-library/images/field-flags.png" >

### Field "Override flags" section

Next to "Default flags" there is a section "Override flags". In this section is possible to define a list of conditions with their flags that should be applied if condition would be evaluated as a true.

Depends on condition outcome (true or false) it is possible to change following field properties:
* require
* visibility
* read only
* read only visibility when there is no value

<img src="/_books/hdoc-library/images/field-override-flags.png" >

List of conditions is evaluated in the order of apprence one by one and it stops on first condition evaluated as true.

### Condition construction

<img src="/_books/hdoc-library/images/field-flags-condition.png" >

To create condition you need to define 3 options:
* "Name" - will be present on the list in "Override flags" section
* "Set Flags To" - here is definition of flags and how it would be set when condition is true
* "If The Following Is True" - this is the place where you define condition (could be more than one)

### "If The Following Is True" section

This is the section where you actually define your condition. It's split on three parts.
* first is field you want to evaulate 
* second is comparision operator
* third is actual value you want to use with operator

For example, on screenshot below you can see that if field is equal to value "yes" then is evaluated as true.


### Comparision operators

<img src="/_books/hdoc-library/images/field-condition-operators.png" >

|Operator|Description|Expected type of value|Example values
|-|-|-|-|
|**==**|equal|number or string|"**yes**", "**5**"|
|**!=**|not equal|number or string|"**yes**", "**5**"|
|**<**|less than|number|"**5**"|
|**>**|bigger than|number|"**5**"|
|**<=**|less or equal|number|"**5**"|
|**= >**|bigger or equal|number|"**5**"|
|**is in**||comma separated number or string|"**any,of,it**", "**1,2,3**"|
|**is not in**||comma separated number or string|"**any,of,it**", "**1,2,3**"|
|**is set**||true if any value is present|
|**is not set**||true if not value present|
|**starts with**||number or string|"**Hello**", "**0**"|
|**ends with**||number or string|"**Bye!**"|
|**contains**||number or string|"**specific**", "**10**"|
|**doesn't contain**||number or string|"**specific**", "**10**"|


:::tip
Please note that not every type of value make sense to compare with every operator, for example for values like numbers use < or > and for strings is better to use starts with or contains.
:::

### Displaying Conditional Fields
* Add a new form field to a capture form and untick the `This field will be visible on the form` option under the Default Flags tab
* A new Override flags tab will be visible next to the Default Flags, navigate here and select Add new condition
* Give the condition a name and choose options such as `This field will be visible on the form`
* Using the `If the following is true` option to add conditions under which this field will be shown / hidden, this can be based on a combination of values (answers) to other questions (fields) on the same or previous capture forms. Select apply Settings when finished.
* It is possible to set multiple sets of Conditions under which a field may be shown. Simply add more conditions under the Override Flags tab using the Add new condition option
* Where multiple conditions are listed, these will be evaluated from the top down until a match is found, the evaluation will stop here and no further conditions will be checked.
* Complete the `Field Type Settings` options to define the attributes of the conditional field.